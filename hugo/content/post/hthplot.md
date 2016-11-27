+++
description = ""
keywords = [
]
date = "2016-10-27T11:34:22+11:00"
title = "Hearthstone.cards.plot()"

+++

I have been enjoying Hearthstone's new Content __'Whispers of the Old Gods'__ and the thought occurred to me while trying to find the optimum mana curve
for my deck, what would the curve look like for the entirety of the game? Rather than doing a boring looking bar chart like the one Blizzard gives
us, I sought to make something different and here it is.

![Hearthstone Plot](img/hthplot/plot.png)

The program first makes an AJAX (Asynchronous JavaScript And XML) request using jquery to the lovely __api.hearthstonejson.com__ and asks for the
English version of the latest cards that people can use (there are cards which are internal and unused).

This returns a JSON (JavaScript Object Notation) file which is parsed into an array of cards.
So to recap, we ask them for all the cards and they give them to us in an array.

We now create another array which keeps track of how many cards fall into the same slot on the graph (so we can make different coloured circles)

We now using JSGMF (my JavaScript Framework) to create a canvas and initialize it before drawing all cards to it based on their cost and
health/attack (or power/strength if you are an MTG person).

The user of the graph can zoom in, change the size of the circles and hide parts of the graph to their liking.

![Hearthstone Plot](img/hthplot/controls.png)

If you are interested go check it out, here is a link to download a .zip of the website.

Signing Out,

-Ewan
