<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Runescape bot detection

**Building AI course project**

## Summary

The goal of this project is to build an AI-based program that could decide whether a character that farms a boss in Old School Runescape is a bot. Old School Runescape is a massively multiplayer online role playing game (MMORPG) developed and published by Jagex Ltd.


## Background

Many massive online role-playing games, such as Old School Runescape (OSRS) developed by Jagex, are infested with _bots_: player characters that are not in fact controlled by a real person. Such accounts disrupt the experience of legitimate players, by, for example, manipulating the ingame economy and spamming disruptive messages. It can be very difficult to reliably tell whether a certain character is a bot or not. To make matters worse, there are many different kinds of bots. Some bots spam messages at ingame banks, some just mine massive amounts of iron ore and some kill mechanically complex bosses 24/7. Tackling all kinds of bots with one program is most likely not feasible, so in this project I am focusing only on bots that are made to repeatedly kill (_farm_) a specific boss. 

The goal of this "project" is to create a program that could decide whether a boss farming account is a bot. 

If such an AI-based program worked, it would solve some long-standing game integrity problems in OSRS. Boss hiscores, which record the amount of kills players have at each boss, are nowadays quite uninteresting. Who cares about your rank, since mosts of the accounts with high amount of kills are likely bots? Another impact of bot farms is the devaluing of the unique items dropped by the boss. Suppose the boss dropped a powerful sword, that is not obtainable elsewhere. The value of the Sword in the ingame economy is determined by (among other things) its rarity. If a bot farm of 2000 bots farmed the boss 24/7 even for a week, they could flood the market with swords, causing their value to crash. This leads to a possibly significant decrease in the profits (and enjoyment?) of the legitimate players. 

Personally I love Runescape. I would also love to see the game flourish, but right now it seems that bots are a big problem. Most bosses and resources in the game a farmed by them. 

Here are some problems/challenges that I can think of: 
* The amount of false positives must be made very close to zero. Banning a legitimate player from the game would be disastrous for PR. 
* Botting programs are constantly evolving, so the detection tool must evolve as well. Reinforcement learning?? 
* Runescape is a very repetitive game. Catching repetitive bots can be harder than it might seem, since real players tend to play very repetitively as well. 


## How is it used, and AI-methods

Personally I do not think I could ever get access to the data that this solution requires. However, Jagex employees certainly have access to it. 

Data that can be used, regarding each player character or account: 
* Order of actions: what does the character do ingame? Which keys are pressed? Where does the player click? 
* The name of the player character
* Playtime: how many hours have been played on the account in a certain time period and how many Bosses have been killed in that time.

Such data would be collected from a vast number of accounts whose bot-or-not-status is known.

I do not really know what AI methods would work the best here, but I would probably try to apply neural networks. The parameters of each player would act as the input, and as an output one would get a probability score between 0 and 1. The closer the score is to 1, the more likely the account is a bot. What happens in the hidden layers is a complete mystery to me. 

It would probably not be very wise to calculate the score for every player every time they kill a Boss. Maybe a bot-check could be made every 100 kills or if some other thing in the character's behavior raises a red flag. 

If the bot-score is large enough, say over 0.95, that account will be flagged as a highly potential bot. Then a human employee could take a look at the account and decide what to do with it. They could ban the bot, or let it run and collect data from it to train the detection program further.

## What next?

To help this project grow I'd have to become a Jagex employee, and that is definitely not going to happen. I can only hope the company's developers are up-to-date with the happenings of the AI-world! 


## Acknowledgments

* Old School Runescape by Jagex Ltd. [Link](https://www.oldschool.runescape.com/)
