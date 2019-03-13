---
layout: post
title:  "Google Cloud DNS, python, and spf records"
date:   2019-02-27 12:08:00 -0600
categories: python code
---

### Problem:
I've been using the python Google cloudsDNS api to create [spf records][spf-records]. The problem was that the TXT record was splitting the value on spaces, which breaks everything. Super fun stuff. Anyways, I spent way to long figuring out what the heck was going on.

### Solution:
Obviously (read with sarcasm), you need to wrap the value in an extra quote. I _guess_ cloudDNS likes TXT records to be lists of string. Heres a code snippet for the off chance someone reads this while tackling the same problem.

{% highlight python %}
zone = self.get_zone(ZONE_NAME)
changes = zone.changes()

# double quotes are here
new_record = zone.resource_record_set(DOMAIN_NAME, "TXT", 300, ['"v=spf1 -all"'])
changes.add_record_set(new_record)
changes.create()
{% endhighlight %}

also, in case you're like me and hate the fact that the "Documentation" link [here][fake-docs] really leads to useless tutorials, here's the actual [api docs][real-docs].

[spf-records]: http://www.openspf.org/SPF_Record_Syntax
[fake-docs]: https://cloud.google.com/python/
[real-docs]: https://github.com/googleapis/google-cloud-python/tree/master/dns
