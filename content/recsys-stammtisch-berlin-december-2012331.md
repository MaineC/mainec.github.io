---
title: "RecSys Stammtisch Berlin - December 2012"
date: 2012-12-30T12:40:20+01:00
tags: [Mahout,Science,recommendation,music,General,]
---

# RecSys Stammtisch Berlin - December 2012


Earlier this month I attended the <a href="http://recommenders.de/">fourth Recommender Stammtisch</a> in Berlin. The 
event was kindly hosted by Soundcloud - who on top of organising the speakers provided a really yummy buffet by <a 
href="http://www.kochzeichen.de/">Kochzeichen D</a>.<br><br>With <a href="http://musicmachinery.com/">Paul Lamere</a> 
the evening started with a very entertaining but also very packed talk on why music recommendation is special - or put 
more generally why all recommender systems are special:<br><br><ul><br><li>Traditionally recommender systems found 
their way into the wild to drive sales. In music however the main goal is to help users discover new content. 
<br><li>Listeners are very different: Ranging from those indifferent to what is being played (imagine someone sitting 
in a coffee bar enjoying their espresso - it's unlikely that those would want to influence the playlist of the shop's 
entertainment system unless they are really annoyed with it's content). There are casual listeners who from time to 
time skip a piece. There are more engaged people who train their own recommender through services like last.fm. Finally 
there are fanatics that are really into certain kinds of music. Building just one system to fit them all won't do. Also 
relying on just one signal won't do - instead you will have to deal with both, content signals like loudness plots as 
well as community signals.<br><li>Music applications tend to be highly interactive. So even if there is little to no 
reliable explicit feedback people tell you how much you like your music when skipping, turning pieces louder, 
interacting with the content behind the song being played.<br><li>In contrast to many other domains music deals with a 
vast item space and a huge long tail of songs that almost never get interacted with.<br><li>In contrast to shopping 
recommenders however in music making mistakes is comparably cheap: In most situations music isn't purchased on a song 
by song basis but based on some subscription model. That way the actual cost of playing the wrong song is low. Also 
songs tend to be not much longer than 5min so also users are less annoyed when confronted with a slightly wrong piece 
of music.<br><li>When implementing recommenders for a shopping site it is to be avoided to re-recommend stuff a user 
has purchased already. This is not the case in music recommendation. Quite the contrary: Re-recommending known music is 
one indicator for playlists people will like.<br><li>When it comes to building playlists care must be taken to organise 
songs in a coherent way, mixing new and familiar songs in a pleasing order - essentially the goal should be to take the 
listener on a journey.<br><li>Fast updates are crucial: Music business itself is fast paced with new releases coming 
out regularly and being taken up very quickly by major broadcasting stations.<br><li>Music is highly contextual: It 
pays to know if the user is in the mood for calm or for faster music..<br><li>There are highly passionate users that 
are very easy to scare away - those tend to be the loudest ones influencing your user community most.<br><li>Though 
meta data is key in music as well, never expect it to be correct. There are all sorts of weird band and song names that 
you never thought would be possible - an observation that also <a 
href="http://blog.isabel-drost.de/index.php/archives/272/apache-con-%E2%80%93-last-day">Ticketmaster</a> made when 
building their ticket search engine.<br><li>Music is highly social and irrational - so just knowing your users friends 
and their tastes won't get you to being perfect.<br></ul><br><br>Overall I guess the conclusion is that no matter which 
domain you deal with you will always need to know the exact properties of that domain to build a successful 
system.<br><br>In the second talk Brian McFee explained one way of modeling playlists with context. With that he 
concentrated on passive music discovery - that is based on one query return a list of music to listen to sequentially 
as opposed to active retrieval where users issue a query to search for a specific piece of music.<br><br>Historically 
it turned out to be difficult to come up with any playlist generator that is better than randomly selecting songs to 
play. His model is based on a random walk notian where the vertices are songs and edges represent learnt group 
similarities. Groups were represented by features like familiarity, social tags, specific audio features, metadata, 
release dates etc. Depending on the playlist category in most cases he was able to show that his model actually does 
perform better than random.<br><br>In the third talk Oscar Celma showed some techniques to also benefit from some of 
the more complicated signals for music recommendation. Essentially his take was that by relying on usage signals only 
you will be stuck with the head of the usage distribution only. What you want though is to be able to provide 
recommendations for the long tail as well.<br><br>Some signals he mentioned included content based features (rythm, 
BPM, timbre, harmony), usage signals, social signals (beware of people trying to game the system or make fun of it 
though) and a mix of all those. His recommendation was to put content signals at the end of the processing pipeline for 
re-ranking and refining playlists.<br><br>When providing recommendations it is essential to be able to answer why 
something was recommended. Even just in the space of novelty vs. relevancy to the user there are four possible 
strategies: a) recommend only old stuff that is marginally relevant to the specific user: This will end up pulling up 
mostly popular songs. b) recommend what is new but not relevant to the user: This will end up pulling out songs that 
turn your user away. c) recommend what is relevant to the user but old, this will mostly surface stuff the user knows 
already but is a safe bet to play. d) recommend what is both relevant and new to the user - here the real interesting 
work starts as this deals with recommending genuinely new songs to users.<br><br>To balance discovery with safe 
fallback go for skips, bans, likes and dislikes. Take into account the user context and attention.<br><br>The final 
point the speaker made was the need to take into account the whole picture: Your shiny new recommendation algorithm 
will just be a tiny piece in the puzzle. Much more work will need to go into data collection and ingestion, into API 
design.<br><br>The last talk finally went into some detail of the history of playlist creation - back from music 
creators' choices, via radio station mixes, mix tapes and finally ending up at spotify and fully automatic playlist 
creation.<br><br>There is a vast body of knowledge on how to create successful playlists e.g. among DJs that speak 
about warm-up phases, chillout times, alternating types of music in order to take the audience on a journey. Even just 
shuffling music the user already knows can be very powerful given the pool of songs the shuffle is based on neither too 
large (containing too broad types of music) nor too small (leading to frequent repetitions). According to Ben Fields 
the science and art of playlist generation and in particular evaluation is still pretty much in it's infancy with much 
to come.
