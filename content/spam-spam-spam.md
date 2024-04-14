---
title: "A short, incomprehensive history of spam and counter measures"
date: 2024-04-11T11:38:28+02:00
tags: [ranking, recommendations, adverserial learning, learning to rank, spam, social media, hacks]
---

# A short, incomprehensive history of spam and counter measures
"... it should be clear that improvements in communication tend to divide mankind ..." by Harold Innis in Changing Concepts of Time

This post was triggered by multiple conversations in my big data circle of friends. All conversations agreed on some important topics: Social media sites these days are influential on the daily life of people globally. With that influence comes an incentive to use these sites to influence behaviour and public opinion. Oftentimes counter measures to these influencing activities - if implemented - are considered the secret sauce of each individual site: Even if malicious users will have a laundry list of sites to spread their message to.

Back in 2022 we had a [keynote](https://youtu.be/oTZyGkG4uTA?si=aXKv87P4uQ6QNBhq) at Berlin Buzzwords on the influence of targeted advertisement on public opinion and on it's detrimental effect on democracy if used in democratic voting processes due to its nature of being invisible to public inspection. After seeing the talk, I've shared the recording over and over again. I believe it is a great talk to explain the field that recommendations and personalised ranking has moved into: From merely suggesting other books or boots to buy based on purchase history, or suggesting other songs to play from play history we have entered a time where recommender algorithm implementations are being targeted by entities actively trying to figure out ranking factors from the outside in order to maximise the impact of their messages on political outcomes.

The fun and encouraging observation though: Malicious actors trying to guess from the outside how training machine models work from the outside - that's nothing new. There's an entire research field called [Adversarial Learning](https://en.wikipedia.org/wiki/Adversarial_machine_learning) dedicated to that topic. I first encountered it talking with people working on e-mail spam decades ago.

However attackes on social media sites aren't trivial cases of mails being sent out. There's entire sub graphs of synthetically created user accounts used to amplify messages. But wait a minute: Again, this is no news for those who remember things like [Google Bombs](https://en.wikipedia.org/wiki/Google_bombing) from decades ago. There's a ton of wisdom in the search engine ranking community about combating search engine spam and boosting organic looking content. A lot of that is based on making sure pages develop organically over time, but also based on properties of the web graph - where pages are nodes, links are edges. Social graphs aren't that different. Well, except if you check the literature on social graphs you will find several features that will set these graphs and sub-graphs apart from mechanically created graphs.

Looking at how [trust and safety teams used to work](https://www.wired.com/story/del-harvey-twitter-trust-and-safety-breaks-her-silence/) what strikes me as obvious is that there needs to be way more integration with those teams working to improve rankings. There are several naive assumptions in machine learning models for learning to rank and for recommending content that are not true - in particular when faced with actors intend on using the ranking signals to their advantage. Knowing these influences though can be [used by platforms to demote](https://www.wired.com/story/youtube-algorithm-silence-conspiracy-theories/) content they do not wish to promote.

Malicious influences though do not happen in an isolated way. Much [like in security](https://youtu.be/7MnZsNW0uwY?si=3M-hk685483lgiz_) - knowing that attacks happen in a coordinated way where players essentially have a laundry list of platforms to target, we need to shift to collaboration in order to gain speed by sharing learnings, both about the nature of attacks but also about working counter measures.

So what does it take, to spread [behavioural changes through social networks](https://press.princeton.edu/books/hardcover/9780691175317/how-behavior-spreads)? Actually quite easily, so in different ways then you would see with deseases spreading in the same networks. You can [play around with such dynamics easily online](https://ncase.me/crowds/).

Naturally I would love to see this collaboration happen rather sooner than later - unless it's already taking place, in which case: Awesome! (Even if I'd love to hear a talk about that at Berlin Buzzwords analogous to the one on security at FOSS Backstage ;) 

One final parting note: A lot of the engineers working in ranking and recommendation may not have witnessed the early days of search engine spam so, maybe it's time to share a few fireside stories as well.
