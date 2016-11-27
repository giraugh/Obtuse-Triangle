+++
description = ""
keywords = [
]
date = "2016-10-27T12:30:28+11:00"
title = "Why Walk When We Would Win?"

+++

To be honest the title is a bit misleading, it should really be _“Why walk when you could fly?”_, I was just going for the alliteration. When creating things we can fall into the trap of using what works best for us and what when we sit down to work, we start doing.

For me this was Game-Maker, and don’t get me wrong; I really like Game-Maker, but it has its flaws (especially when making certain types of games). Normally I just put up with it and keep working away but recently I hit a wall, a very annoying wall. I had just finished up a tileset for a new project when I realised that if I wanted certain tiles to be solid, I would have to split each tile into its own sprite and at the time I had over 45 tiles. I then though to myself “Why don’t I just use a different engine?” and so I did.


## Unity (C#/Javascript)
First engine to try was Unity, and it worked out alright except when it came to simple things like animations. At the time I was using (and still am tbh) some placeholder art from Nuclear throne and I had a single run animation which I wanted to pause when I stopped moving. Unity required (even in 2d) for every object with animation to have a state machine and I COULD NOT for the life of me get it to have a state which just paused the animation or even just went back to the first frame. The only alternatives it seemed was for me to make my own animation system or to use something from the Asset Store (and I wasn’t keen on spending money just to get around this problem)

_For those who do want to use unity and are having the same difficulty, Powerhoof recently unveiled [a tool](https://www.assetstore.unity3d.com/en/#!/content/71177) which helps with this exact problem, unfortunately it costs $10._

## Unreal (C++)

Unreal was my next stop, for some reason I kept going to 3d engines, I was hoping that this one was gonna be good and I didn’t stop to check if it supported 2d, short answer: no.

## Mono-Game (C#)

I was really impressed with MG in nearly every way…except its resource management. It required you to create resource packs for use within the game and it seemed it wouldn’t be bad if you could get its pipeline editor too work, which for some reason wasn’t included with my installation and I also couldn’t find a binary for it and would have to had built it myself. Either way, I had already started something else by this point which was going better so I gave up on MG.

## LÖVE2D (Lua)

Love was quite a breath of fresh air from the other engines, it didn’t get in your way and screw stuff up and it also provided lots of functionality, and what it didn’t provide, [the community did](https://github.com/love2d-community/awesome-love2d). However Love uses Lua, which despite some really cool tables and good ideas with metatables, has a really weird syntax and a distinct lack of classes.
_(note that there are ways of adding classes through [external packages](https://github.com/love2d-community/awesome-love2d#helper-libraries))_

That was when I found Moon-Script, a precompiler for lua which adds classes and coffeescript’esque syntax (significant white space e.t.c.). This was a big breakthrough, yet it didn’t solve all my problems with Lua (and it also introduced [some](https://github.com/leafo/moonscript/issues/14) [more](https://github.com/leafo/moonscript/issues/35)). For this reason I set out to create a precompiler for Moon-Script which would add some nice features and syntax changes which i desired.

And so, [Moon-Shine](https://github.com/retroverse/MoonShine) was born. In an effort to try something new it was written in Go and didn’t use a lexer/parser and instead entirely relied on Regular Expressions.
_(Yes I do know that regular expressions are not as fast, but the language is very minimal and writing a lexer/parser wouldn’t make it much faster and would have just taken me longer to write)_

## The Next Trial

Ah, this game wasn’t gonna just start working for me, next hurdle: A level editor. I checked out some level editors such as Tiled and decided they were overly complex/not a good fit for my game and decided to put one together instead . I had actually made [a level editor before](http://tdos.itch.io/chivalry  ) but it was very much integrated into Game-Maker so I had to start from scratch.

I decided to make it in C# _(Making up for not using Unity :D)_ and try to make it as general as possible in order to not get a repeat of last time. In order for it to be easily reusable it had to be able to load run time data (so you don’t have to build it from source) and so I opted to use YAML for my data as it was nice and human readable.

[!Yaml Data File](img/why-walk/yaml.gif)

Unfortunately loading YAML in C# wasn’t as easy as expected (that’s a story for another day) but I pushed through and put together Lime-Editor (Lime being the game).

[!Lime-Editor in action](img/why-walk/editor.gif)

So, when making your games or projects or whatever you do, remember (and I will try too) not to struggle on if your tools aren’t working with you and if you can’t find tools that do, make your own. Good luck!
-Ewan
