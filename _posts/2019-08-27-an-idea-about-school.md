---
layout: post
title:  "A Different Way to Structure College"
date:   2019-8-27 6:0:00 -0500
categories: random thoughts
---

There's a large variation of college experiences among me and my developer coworkers. Some of us (like me) have computer science bachelors degrees, others have only taken a couple relevant classes, while others have come from completely different fields and were self taught. The one thing that's blatantly apparent to me is that the degree I have doesnt make me a "better" developer. Does that make the normal 4 year university a scam?.. Well maybe, but the more interesting thing to me is the discussion of how Universities could be structured __differently__ to be of a higher value to people. I have 3 thoughts and an idea on this. Also remember that these are mostly the thoughts and opinions of some random 24 year old, so their probably extremely overgeneralized and naive. If you think I'm off base on any of this, I'd love to know why!

---

![approximate knowledge of many things](/assets/images/approximate_knowledge_of_many_things.gif)

### Thought 1:
We put up arbitrary "walls" around a topic and call it a "class". I get why this happens, it seems like a natural way of doing things. Teachers or professors have a certain pool of knowledge, and that pool is the only thing they can (or at least should) teach from. The whole point of academics seems to be to create people like that.  My grandfather, a gifted chemist, used to say his whole life was "learning more and more about a narrower and narrower subject, until eventually he'd know everything about nothing". To me that's what universities are trying to do to you. I'm not saying there's anything specifically wrong with that, expertise in a single narrow subject is a powerful thing. However, that's not what I want. The joy and goal of learning is not only deepening knowledge on a single subject, but breaking down those walls between subjects to make connections between them. Jack of all trades, master of none, is often better than a master of one right?

But college is all about that type of learning isn't it? Did I forget that gen eds take up around half of all your classes. No I didn't forget, I just think thats an illusion. Its an illusion because those "gen ed" classes are not structured around making connections to your major (in my case computer science). Those classes are built to act as gateways into their own majors, or worse to be the feared "weed out class". To give an example, a chemistry 101 class is all about building a base for your eventual Chem 3XX classes, not to give you the "jack of all trades" knowledge in chemistry. At best, the (often random) gen ed classes someone chooses happen to cross pollinate with your chosen profession. At worst, you spend thousands of dollars to take a class where you forget everything a week after its done because it "wasn't your major". This brings me to my second thought.

### Thought 2:
How much of any college do you remember? What about ones within the field of your current profession? What about that one random gen-ed about clouds or something? We spend A LOT of money to take classes we forget 90% of. Why is that? Clouds are cool, and how the earth's weather works is important for a person to know (more so now with the seeming increase in extreme weather events around the world). I think it comes back to thought 1, where the class if really there to start your path to "an expert in Meteorology", not someone who knows how the weather works. To give classes a little slack, it probably has just as much to do with people going into the classes expecting to forget it. The question "When will I ever use this?" has probably shut down countless people's willingness to learn.

### Thought 3:
This one is more specific to computer science. We teach it backwards. Or maybe a better way to put it is we teach it upside down. The first programming class I took was in Java (please don't email me your opinions about Java as a language). I know python is another popular first language choice. You learn all the cool things including variable, lists, if statements, etc. But thats the top of the stack, thats 75 years of layer after layer of abstraction. The moment you peek past a curtain 1 layer deeper, you're completely lost. Everyone who's taking more than 1 comp sci classes remembers pounding there heads on a "null pointer exception" for the first team after leaving the nest of garbage collectors. To me a better way to teach computer science is bottom up, building the abstractions.

---

![infomercial](/assets/images/infomercial.gif)

### There's just got to be a better Way:
here's my idea of a different way to approach teaching Computer Science (though this could work for any field). You take 1 main "computer science" class, or maybe a better word is a "track". Instead of starting with the highest level and maybe peeling back some layers of abstractions, you start at the bottom. The track is all about building those layers just like they were through history. That means for a long while there is no programming, at least not the tradition kind. You go though a topic, then at the end you put it in the "black box" and use it in the next layer. Boolean logic becomes logic gates, logic gates become half adders, half adders (plus some other stuff) becomes cpu's, cpus to assembly, assembly to compilers, on and on it goes. The benefit to this is that there is no "magic". Each new topic is simply an extension or use of the previous. There is also a nice parallel to the actual hardware. Students could build the logic gates out of dominos, then later use breadboards to build half adders. Later this track branches into more specific sub fields (web, graphics, ai, security). Maybe the course branches, but later comes back together, only to branch again.

While this master track is happening, you take what I'll call the "satellite" track. Theses are month long classes on non computer science topics, also following a natural flow. Maybe for a year you focus on the earth, moving from geology to chemistry to biology to anthology ect. The main idea of these classes is to give you the "jack of all trades" knowledge. It's the stuff you'll actually use and remember. Since these classes are so short, they could be as specific or general as makes sense. A class about taxes in your current country/state is useful, so is a class on the basics of philosophy. Just like the main course this track can branch and join where it makes sense.

here's a diagram that I hope helps explain what I'm thinking:

```
+-------------------------------------------------------------------+ +-------------+
| Major Classes                                                     | | Satellites  |
|                                                                   | |             |
|              boolean logic                                        | | geography   |
|                   +                                               | |   +         |
|                   v                                               | |   |         |
|              logic gates                                          | |   v         |
|                   +                                               | | Weather     |
|                   v                                               | |   +         |
|              half adders, apu, etc                                | |   |         |
|                   +                                               | |   v         |
|                   v                                               | | Chemistry   |
|              a basic computer                                     | |   +         |
|                   +                                               | |   |         |
|                   v                                               | |   v         |
|              assembly                                             | | Biology     |
|                   +                                               | |   +         |
|                   v                                               | |   |         |
|              compilers + interpreter                              | |   v         |
|                   +                                               | | Anthology   |
|                   v                                               | |   +         |
|              C, pointers, memory alloc, etc                       | |   |         |
|                   +                                               | |   v         |
|                   v                                               | | Philosophy  |
|              higher level languages, functional programming       | |             |
|                             +      +        +                     | |             |
|                             |      |        |                     | |             |
|                             |      |        |                     | |             |
|                             |      |        |                     | |             |
|                             |      |        |                     | |             |
|                             |      |        |                     | |             |
|  graphics     <-------------+      v        +---------->  web dev | |             |
|                                security                           | |             |
|                                                                   | |             |
|                                                                   | |             |
|                                                                   | |             |
+-------------------------------------------------------------------+ +-------------+

```

The biggest challenge to this approach is who teaches it. You'd either need 1 person who can teach "the whole stack", or pull in the right teacher for the current topic (that would require a lot of communication between the teachers to keep things flowing). The second approach would also allow for students to start in staggered groups, instead of all at once (like kids singing Frère Jacques in rounds). The other challenge with this is I have no idea whether or not it works. Maybe something like this is already implemented and working at some hipster college on the west coast.
