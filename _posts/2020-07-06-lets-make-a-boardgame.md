---
layout: post
title: "Let's Make a Board Game: Phallanx "
date:   2020-07-06 12:08:00 -0600
categories: games design
excerpt_separator: <!--more-->
---

I'm a huge fan of the game of Go, which I've been playing (very badly) for a little over a year. I love how old it is (it's believed to be the oldest board game still actively played), the minimal required pieces of just black and white stones, and the fact that the (relatively) small ruleset leads to something extremely complex. And although the "official" game is played on a 19x19 board, there's something about the smaller beginner 9x9 board that especially resonates with me.

Well as someone who loves to make games, I couldn't resist making my own game that incorporated all the things I love about Go. Here's what I came up with!

<!--more-->

### Phalanx

![phalanx](/assets/images/phalanx1.jpg)

Phalanx is a game that I like to think could existed during the Hellenistic period. Its themed around the greek Hoplites and (as the title suggests) the Phalanx they form. Players take turns taking actions to move or reenforce their armies, with the goal of reaching their temple on the other side of the board. You can also push or slide a whole line of pieces to isolate and kill the opponents pieces! Completely eliminating the opponents pieces will also bring you victory, so you'll need to balance trying to rich your goal without exposing yourself to attack.

Here's the complete rule set:

> __Goal:__
>> Either remove all opponents pieces (hoplites) from the board or connect to your goal. The game ends immediately when one of these conditions are met.
>
> __Required Pieces:__
>
>> - A 9x9 plain grid of 9 horizontal and 9 vertical lines
>> - 9 black and white stones each
>> - 1 black and white Goal (can be a unique piece or a 10th stone)
>
> __Setup:__
>> For each player place 4 stones in the shape of a square in adjacent corners of the board 1 intersection away from the wall. These are your starting hoplites. Place 1 stone each in the opponent's corner (behind the square); This is your goal.
>
> __Life & Death:__
>> 2 hoplites are connected if they share an adjacent intersection. 2 or more connected hoplites are considered a living phalanx. A hoplite is dead if they are not connected to another hoplite, or if they are pushed off the board (more below). Dead hoplites are immediately removed from the board.
>
> __Flow of Play:__
>> Black takes the first turn, then players alternate back and forth. A turn consists of doing optionally up to 3 actions. The same action may be done multiple times. The possible actions are:
>>
>> - MOVE: move 1 hoplite to an adjacent intersection touching their army. You may split or merge phalanx, but hoplites may not jump between unconnected phalanx.
>> - RENFORCE/ADD: If you have less than 9 hoplites on the board, add a new hoplite to an existing phalanx
>> - PUSH: if your phalanx is connected to an opponent's, and the number of your hoplites is greater then the opponents in a straight line, and there is an open intersection on the other side of the line, you may slide the whole line towards the opponent's hoplites 1 intersection. Hoplites pushed off the board are dead.

[And here's a printable version with pictures](https://docs.google.com/document/d/154r83vmF71kw7s2ygqZgPeT9UemsDekU2zTiB-olOq4/edit?usp=sharing)

![phalanx2](/assets/images/phalanx2.jpg)

My wife and I have been playing this game relatively unchanged for a couple months and I'm really happy with how it turned out. No one winning strategy has appeared and I still feel like we're discovering new strategies, army shapes, and pitfalls. We've had success keeping all the stones in 1 big blob or splitting them up into different smaller armies, so when you play don't be afraid to be creative!

### Inspiration & Design Process
Phalanx started out as "worms". inspired by the classed "Snake", I had the idea of moving connected pieces around to simulate worms crawling around and growing. But very quickly I realized it looked a lot more like armies moving on a battlefield, so I ran with that.

I knew there needed to be some way to remove enemy pieces. During this whole process I was reminded of John Conway's (who had recently passed away) Game of Life. In it there's a rule that if a piece is by itself, it's dead and is removed. That was perfect!..but I still needed a way for players to isolate stones. I experimented with a bunch of ideas, but landed on a mechanic where you could "push" or "slide" a whole line if you had more pieces in that line & you were touching an enemy piece. You could push stones isolating one to die, or push a stone off the board. This felt pretty novel, and quickly became the focal point of the whole game. It also allowed for stuff like multi-piece-kill combos or choosing to sacrifice your own pieces, which gave some nice complexity. The only downside I've found is that the rule is a little hard to explain, but a couple examples usually clears things up. The win conditions, balancing, and theme came really naturally after this mechanic!

One problem I'm still figuring out is that player 1 has a pretty strong "first move" advantage. The current solution is to give player 2 an extra starting stone, which "works" but I'm not a big fan of the asymmetry so that will probably change. I'll also need to tweak the written rules to include these clarifications that have come up when teaching the game to people.

- "can pieces be moved around the edges of the board?" (Yes)
- "Can you push the opponent if you're also blocking them on the other side of the line?" (No)

### Programming

I'm also currently working on an implementation of this game in [Fennel](https://fennel-lang.org/). Using lisp in an actual project has been a dream come true, and I'm happy to say it's been serving me well. Ive been using [love2d](https://love2d.org/) for the graphics, Though my ultimate goal is to publish it on the awesome looking [play.date](https://play.date/).

I've already completed the base rules, a (very dumb) AI, simple graphics and even move undo. I'm excited to create an AI that actually works, a wireframe 3d game board, and a polished UI. As a stretch goal I've been thinking about how I would add multiplayer over the web. The plan is to write independent blog posts for each of these features and post smaller progress reports on the [tigsource forums](https://forums.tigsource.com/). Who knows, I may even make a dollar or 2 when it's all said and done!

You can follow my progress and view the source code [here](https://github.com/AlecTroemel/phallanx/), just please don't create an issue asking me to rewrite it in rust..
