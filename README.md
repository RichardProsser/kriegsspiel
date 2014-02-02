kriegsspiel
===========

For a long time now I've had the idea of playing a umpire-managed multi-player [Kriegsspiel](http://kriegsspiel.org.uk/index.php/articles/origins-history-of-kriegsspiel/3-origins-of-the-kriegsspiel) games online, which avoids the problem of arranging a venue and offers some automation benefits.

I am not sure what software would be suitable for that, though; I imagine some kind of "online meeting" package, with a whiteboard of sorts to display maps. I currently favour [OpenMeetings](http://openmeetings.apache.org) and [Teamspeak](http://www.teamspeak.com) may be useful also.

Basic Requirements
------------------


  * A membership site, with the usual registration and log-in facilities.
  * Communication via Instant Messaging (Chat - written orders) or VoIP (voice - radio).
  * Group management will be necessary, so that umpires can chat amongst themselves and communicate separately with the players/teams.
  * Map display, editable to show unit dispositions and ideally scaleable to allow users to zoom in/out.
  * Record-keeping so that the umpiring duties are spread around.
  * Event-driven game management (see below)


Desirable Features
------------------

  * A Save/Restore game state option, to allow a game to take place over several sessions
  * Automate message management (queuing), so that couriers etc. may be automatically delayed or captured, possibly with a random element
  * Line-of-sight unit detection, for scouts/observers.
  * Automated conflict resolution - calculations, according to some rules.
  * API to permit third-party development of extensions.

-----------

Event-Driven Game Management
----------------------------
N.B.: the following comments apply to a manual system but may help to drive the design of the computer-assisted version.



Typcially the umpires in a conventional game will organise orders/reports in slots of 15-minute intervals or thereabouts. Whilst that does work it is rather artificial and there may be many occasions when little of interest is happening in the game but the umpires still have to visit the players on a regular basis. All of which requires considerable management effort.

An alternative is to create a diary, with blank entries at intervals; these may be 15 minutes as before but could be 10 or even as low as 5. When an order/report event occurs - e.g. a message is sent between a commanders - then the umpire estimates how long it would take for the message to reach the intended recipient and notes that time in the diary. The same goes for units arriving at their specified destinations, after an order is issued and received.

All the umpires then have to do is wait near the players to get their orders and pass them on to Umpire HQ, or check the Event List to announce the arrival of a courier or whatever. Any clash of units on the field would also constitute an event of course (the report of which should be added to the list), so the umpires would need to be aware of such possibilities. They must also know the current game time of day of course.

Note also that the system can be applied to any timescale - e.g. days or even weeks. It is both efficient and scaleable.
