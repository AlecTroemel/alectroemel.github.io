---
layout: post
title:  "The Mystery of Haproxy, Cloudfront, and S3 Static Sites"
date:   2020-04-10 12:08:00 -0600
categories: haproxy aws code
---

### Problem:
I was attempting to setup an haproxy reverse proxy to an s3 static site fronted by Cloudfront, something like this

```
Haproxy reverse proxy => Cloudfront distribution w/ redirect HTTP to HTTPS => S3 Static Site
```

However with this backend config

```conf
backend broken_backend
    mode http
    http-request set-header Host my_cloudfront_domain.com
    server broken_backend my_cloudfront_domain.com
```

I was getting cryptic `400 unable to handle request` errors.

### Solution:

The solution ended up being all in my haproxy config. After a some google searching I learned that using HTTPS backends in haproxy required some extra config (and haproxy 1.5 or newer). One solution is to not check the validity of a servers certificate. You should only do if you trust the server, in my case I do. The config looks something like this:

```conf
backend still_broken_backend
    mode http
    http-request set-header Host my_cloudfront_domain.com
    server still_broken_backend my_cloudfront_domain.com:443 ssl verify none
```

However then I started to get 503's, which turned out to be a little more nuanced. The solution was to send a Server Name Identification (SNI). Without it Cloudfront doesn't which name you're trying to connect to, and as a result which SSL certificate to use. Cloudfront handles this problem just close the connection, causing haproxy to throw a 503.

Everything together looks like this:

```conf
backend working_backend
    mode http
    http-request set-header Host my_cloudfront_domain.com
    server working_backend my_cloudfront_domain.com:443 ssl verify none sni str(my_cloudfront_domain.com)
```

I wish [this section in the docs](https://www.haproxy.com/documentation/aloha/9-5/traffic-management/lb-layer7/tls/#define-server-settings) would have shown up earlier in my research, the phrase "SNI" ended up being the key to unraveling all this.. Maybe this article will help google's magic algorithm connect the dots a little better.
