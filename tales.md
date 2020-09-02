# Tales of the Auld Ones

> Once upon a time, in a space station far, far away...

This page is meant to collect some stories from the early days of Tau Station.

## Shadow's Tungsten Clava

(recounted from moritz's memory, so possibly inaccurate).

In the days of the closed alpha testing (and before the Public Market or
CORETECHS storage management existed), ser Shadow told us in the chat that
he accidentally sold a [Tungsten Clava](https://taustation.space/item/tungsten-clava)
that he was supposed to deliver for his current Discreet Work.

He tried to obtain another copy through scavenging the ruins, but without
any luck. Unwilling to abandon the Discreet Work and to disappoint
his employers, he asked the community for help.

So the other players reading the chat rushed to their storage lockers
to see if they had any Tungsten Clavas left; several through they had,
but were unsure about which stations they were on (and this was
before private ships or Quantum Telephoresis as well, so travel was
slooow), and ser Perleone was the first one to locate one and send
to ser Shadow.

THe non-existence of the Public Market meant that ser Shadow could not
send ser Perleone any money, and unwilling to easily accept a gift,
our dear Shadow had to wait some days until he got his hands on another
Tungsten Clava to send back to Perleone.

For maybe half a cycle afterwards, players pasted notable occurrences
of Tungsten Clavas into the chat, for example when obtaining two in a
single discreet work (stealing one, and being awarded one).

## The XSS Bug That Stole Your Weapon

(recounted from moritz's memory, so possibly inaccurate).

It must have been in February or March of 2018 that ser Perleone
found a [Cross-Site Scripting bug](https://en.wikipedia.org/wiki/Cross-site_scripting)
in Tau Station, which is a fancy of saying that in the player's blog,
you could include Javascript links, and run them in the player's browser
who clicked on that link.

Instead of a simple demonstration that opened an alert box (the standard
proof of concept for such things), Perleone decided that a more fancy
task needed to be accomplished. So he created javascript that made
you (all hidden in an iframe) go to the Shipping Bay, unequip your primary
weapon, and send it ser Perleone (which implied adding him to your friends
list first).

This PoC was then presented to ser Ovid during an in-person meeting
between Perleone and Ovid at the [2018 German Perl Conference](http://act.yapc.eu/gpw2018/)
in Gummersbach near Köln.

The Bug was fixed a few days later.

## Gold Rush

(recounted from moritz's memory, so the timeline might be slightly off).

'twas the Ides of October 2019 when a [game update introduced variable station economies](https://taustation.space/blog/update-changelog-2019-oct-15/),
which (among other things) affects item prices at NPC vendors -- both for buying and selling items.

Some players started to notice that previously pretty worthless items, like stims, suddenly achieved
quite the high prices when sold to NPC vendors.

Several test transactions were conducted by TAU and TTU syndicate members, involving
somewhat light items (to avoid high shipping costs) being purchased on one station, sent
to another player on another station, and being sold there for a considerable profit.

It was evening, and it was morning, the second day.

Your humble narrator, ser moritz, was at Barnard's Star, and sent all his tier 3 stims from
previous salvaging, discreet work and look-for-trouble to ser Brovnik over at Spirit of
New York City in the YZ Ceti system, who sold them for a considerable profit (in the lower
single-digit million credits range), which after subtracting shipping costs, was amicably shared
between the two partners involved in the transaction.

It was evening, and it was morning, the third day.

The station economies continued to go into extremes, and some enterprising merchants noticed
that huge price gradients were present even within systems.

Enterprising souls, including your humble narrator, went to a low-economy stations in YZ Ceti
(it might have been CVS or ASI), bought stacks of stims there (because they have the highest
price-to-mass density), traveled to SoNYC and sold them there. Traveling to SoNYC was *really*
expensive by public shuttle, on the order of 20k credits for a local shuttle ticket, but that
was worth it.

A bug report alerted staff of the potential unintended consequences of the update.

Ser firefu contributed a userscript that added a "buy stack" and "sell stack"
buttons to the NPC vendor and inventory UI, and was awarded several million
credits by other TAU and TTU members for this contribution to sanity and
preventing RSI.

It is said that some players made between 5 and 20 million credits that third day.

It was evening, and it was morning. The fourth day.

After midnight rolled around in the Europe/Berlin time zone, the gold rush was over.
Station economy factors are now limited in a way that prevents people from buying
items on a low-economy station, and selling them for profit on a high-economy station.

It was evening, and it was morning. The fifth day.

Economy factors are wild again, it seems the limiting of economy factors either was
beset by bugs, or not properly deployed to production. Whatever it was, Gold Rush
was back for another day.

Staff was informed, and the sentiment ranged from "go for it, one last day of
easy profits!" to a weary "more clicking? What do we need credits for, anyway?".

It was evening, and it was morning. The sixth day.

Gold Rush was officially and permanently over. Let's call it *lead morning*.

It was evening, and it was morning. The seventh day.

Staff rested.

