---
title: "The Beginning of DRI"
description: "Big (Commander) Deck (sus) Problems"
pubDate: "Oct 07 2026"
heroImage: "/rubber-ducky.jpg"
---

# Time flows  
## When are we?  
### Now here, of course  
Part of chasing something new is mulling over an idea.  
I did that right away, and that was a not mistake I regret.  
I arrived at this understanding because I
* paused  
* thought about it  
* explored my options  
  
**However**, this is mostly *hindsight*.  
  
### What happened?  
*I know that new projects even if a huge mystery, can be fun.*  
So, the app idea is an MVP phone app that tracks steps, phases, turns, and cards entering leaving the battlefield--with manual input
    
### The piece I am missing  
I have yet to publish a mobile app on App store or Play store
  
Rather than immediately building it, I have created two documents about it. I will skip my reflection and assessment of it for now, and simply
include the contents thereof as a specific example of what research documentation is. It might be bad or good, likely a mix. I might sort it out later.

The Three-Letter-Acronym (TLA) for the app is "DRI". I have an idea what that stands for, Deck R(running/pilot/navigate) Interface.

### Document 1: DRI Flow Log

Logging user interactions before the UI/Logic gets coded

1. Players have the app downloaded/web-page open
2. Player shuffles up and deals their opening hand
	In this example, I will be using Prosper deck because I know it has timing triggers
	Opening hand doesn’t need input, drawing turn 1 to simulate 4-player cmd
	
3. Game loop begin.
	Game start (graphic/animation)
	Untap (graphic)
	--untap permanents
	--pass
	Upkeep (graphic)
	Draw (graphic)
	--draw a card [_]
	--draw a card [x]
	--pass
	Main phase 1 (graphic)
	--land played [_]
	--land played [x] mountain
	--pass
	Combat phase (graphic)
	--pass
	Main phase 2 (graphic)
	--land played [x]
	--pass
	End Step

Turn 2: Mountain; Talisman of Indulgence
Turn 3: Mountain; 
	Main phase 2 (graphic)
	--tap 3 Mountains and Talisman (for black) Prosper, Tome-Bound
	--USER:input Prosper as a card played
	--APP:new timing trigger added to End Step
	--APP:new event trigger added to battlefield (Phase 2 functionality)
	--pass
	End Step
	--trigger prosper
	--card exiled, playable:true
	--APP:new trigger added to “Until end of your next turn…” playable:false

Turn 4: (skipping normal moves for brevity)
	Main phase 2 (graphic)
	--tap 2 Mountains for Charcoal Diamond from exile
	--USER: input charcoal diamond, from exile
	--APP: requires treasure token be generated, (tap to record generation)
	--USER: input cast Share the spoils from hand
	--APP: new event trigger added to battlefield (Phase 2 functionality)
	--pass
	End Step
	--trigger

Turn 5
	Main Phase 2
	--Cast Gonti from exile, create treasure token, no new event/timing triggers
	--tap 3 mountains and sac both treasures, 
	--cast Possibility Storm from exile, make a treasure token, exile top card
	--play the swamp from share the spoils, make a treasure token
	--every card in my hand is super expensive and will not be transformed into cheap crap lol
	End Step
	--trigger

At this point I’m making lots of in-turn plays not dealing with the app, but they are triggering the creating of a treasure token. That said, I do know one of the cards MK played was one that said the first card played from exile gained Cascade. I haven’t gotten that one yet

Turn 8
	Main Phase 2
	--Cast Etali from hand, trigger possibility storm
	--reveal Karazikar, cast it
	--USER: input Care Karazikar
	--APP: new time-trigger events “when you attack…” and “when an opponent attacks…”
	--USER: input Loyal Apprentice
	--APP: new time event with condition, “at the beginning of combat on your turn…”
	--USER: input Wild-Magic Sorcerer
	--APP: new rule “the first spell you cast from exile…”

Other examples: Urabrask, Heretic Praetor; Hellkite Tyrant; Theater of Horrors
Other phase 2 examples: Pontiff of Blight giving everything Extort
Other inputs:
	--USER: input state change, Card removed from battlefield
	--APP: check for triggers due to removal (Phase 2)
	--APP: remove triggers created when card was input by user

Part 2

I selected this commander as an additional introduction of a nifty feature set:
1. Mana tracker
2. Storm count
3. Turn tracker (including players taking extra turns)
4. List of player names for anyone who plays cards that steal other player’s cards in-game

Kruphix, God of Horizons; doesn’t directly care about storm-count, but fuels it
The turn tracker is designed to handle the fact Kruphix changes what happens during
ALL steps and phases, albeit only affecting its controller’s mana pool. 


### Document 2: Outline List from DRI Flow Log
From Flow Log to feature outline/list

For Sale on Android Play store $2.99 
	Price based on product being $1.99 in 2008 when Play store first opened
	Requires testing on android devices and meeting Play store standards
	Test on iPhone if demand for it grows (perhaps a kickstarter campaign)
	Related to log line “Players have the app downloaded/web-page open.”

Externals
	Having a deck
	Assuring the deck is legal in Commander
	Internal: The application must update legality if it ever be a deck-building assist
	
Internal Navigation:
	Shuffle (learn more link → pile into weave shuffle) 
	Offer Cut
	Put the library where it goes
	Reveal commander(s); put it where it goes
	Roll to see who gets to chose to go first/last
	2d6 high-roll wins
	player chooses
	All players draw hands
	First player takes mulligans followed by others in turn-order
	
	After last person declines a mulligan, first player takes first turn of the match
	If you are first player, follow the app instructions, otherwise, pay attention to other players
	Once your turn beings, follow the turn order app instructions, passing after each
	Begin turn
	(large animation)

	Untap Step: You untap all permanents you control
	(small animation)
	Upkeep Step: Triggered abilities happen; players can cast instants.
	(small animation)
	Draw Step: You draw a card from your library.
	(small animation)
	Main phase 1: play a land if you can; cast any permanent/sorcery that will change combat

	(large animation)
	Combat phase
	Beginning of Combat Step: Last chance to stop creatures from attacking.
	(small animation)
	Declare Attackers Step: Choose which creatures attack and who/what they attack.
	(small animation)
	Declare Blockers Step: Defending player chooses blockers.
	(small animation)
	Combat Damage Step: Damage is dealt simultaneously.
	(small animation)
	End of Combat Step: Combat phase wraps up.
	(large animation)

	Main phase 2: play a land if you can; cast any permanent/sorcery that will change game state
	(large animation)

	End phase
	End step: “beginning of end step” triggers go on the stack
	Cleanup step: Max Hand Size vs Current, and damage wears off
	(large animation)

  
***Take Care!***  
Thomas Custer  