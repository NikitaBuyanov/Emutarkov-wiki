# Editing differents things in my player profile
## Requirements
For doing **any** edits in EmuTarkov i higly recommend you to use this software :
* [VSCodium](https://github.com/VSCodium/vscodium/releases)

This software is free and alot more helpfull for alot of things, like missing coma and everything about the syntax.
* Make a backup of the profile you're using.

For this, heads to `ServerFolder/user/profiles` and create a copy of the profile you're using (you should have only one if you don't know what you're doing, and need this tutorial).

**⚠️ If you want to make any changes in your profile files, close both the game and the server, none of these should run ⚠️ .**

It's recommended too to do it on a fresh wiped profile.

## Table :
* [Change your character level](tutorials/edit_the_player_profile.md#editing-my-character-level)
* [Change your skills level](tutorials/edit_the_player_profile.md#changing-my-skills-level)
* [Change your quests status](tutorials/edit_the_player_profile.md#change-quest-status)
* [Change your hideouts areas status](tutorials/edit_the_player_profile.md#changing-hideout-areas-status)
* [Change your traders loyalty level](tutorials/edit_the_player_profile.md#editing-traders) 
* [Add money in your stash](tutorials/edit_the_player_profile.md#Adding-money-to-your-character)

## Editing my character level
In this part, we are going to change your character level in EmuTarkov. For doing this we are going to make edits in the following file : `ServerFolder/user/profiles/accountID/character.json`.

Open the file with VSCodium or Notepad++ and find the following line : **"Experience": 0,**.

This line is defining how much experience your character have, and will define wich level he have, we wont change the line **"Level": 1,** because it's not needed, and not read by the server.

The only thing we will have to do is change this number, by one of the selected level you want. You can know wich experience you need for each level there : [Escape From Tarkov Wiki](https://escapefromtarkov.gamepedia.com/Character_skills) at the end of the page.

The column we want to take the number from is : *Cumulative Total*.

Copy this number and replace the number "0" in your profile and remove the extra coma in the number and keep the last one. For being level 30 for exemple, it should be this :
**"Experience": 781760,**.

Save your changes and start the server, you now have the desired level !

## Changing my skills level
In this part, we are going to change our skills level, for having the master level of each skill. For this, heads to `ServerFolder/user/profiles/accountID/character.json` and search for this in the file : **"Skills":**.

When you will be at this point, you will face this :

```json
"Common": [
			{
				"Id": "BotReload",
				"Progress": 0,
				"PointsEarnedDuringSession": 0,
				"LastAccess": -2147483648
			},
			{
				"Id": "Endurance",
				"Progress": 0,
				"PointsEarnedDuringSession": 0,
				"LastAccess": 0
			},
			{
				"Id": "Strength",
				"Progress": 0,
				"PointsEarnedDuringSession": 0,
				"LastAccess": 0
      },
      [...]
```
Some explanations :
* **"Id":**
  * Determine the name of the skill.
* **"Progress":**
  * Determine the number of points you learned for this skill.
* **"PointsEarnedDuringSession":**
  * Determine how much points you got from the last session.
* **"LastAccess":**
  * Determine the last time you earned a point in this skill (it's a timestamp).

So you gessed right ~~or not~~ that we will have to change the **"Progress":** part of each skill **EXCEPT** the skill **BotReload**.

How to know wich level is your skill, here is some easy math :
* 1 Level = 100 points
* 10 Levels = 1000 points
* 15 Levels = 1500 points

According that the master level of the skill is **51** we will need to have **5100** points in **"Progress":**.

At the end, the line for each skill you want to max out looks like this : **"Progress": 5100,**.


[Back at the top](tutorials/edit_the_player_profile.md#editing-differents-things-in-my-player-profile)
## Change quest status
Well, in this part you will learn how to change your quest status, that means, make it finished without having done the requirements for it (you mainly need to do this when a specific quest is bugged).

For doing this heads to `ServerFolder/user/profiles/accountID/character.json` and search for this in the file : **"Quests":**.

You're going to face something like this when found : 
```json
"Quests": [
		{
			"qid": "5936d90786f7742b1420ba5b",
			"startTime": 0,
			"completedConditions": [],
			"statusTimers": {
				"1": 1585993679.6069999
			},
			"status": "AvailableForStart"
		},
		{
			"qid": "5936da9e86f7742d65037edf",
			"startTime": 0,
			"completedConditions": [
				"59a9269486f7747aab09a77c"
			],
			"statusTimers": {},
			"status": "Locked"
		},
```
Let me explain you these :
* **"qid"**
  * This is the quest ID wich will give you the name of the quest.
* **"startTime"**
  * This is the timestamp when you started the quest.
* **"CompletedConditions"**
  * This is where the requirements for completing the quests are stored. These are ID's.
* **"statusTimers"**
  * This is the timestamp since when the quest is available.
* **"status"**
  * This define the status of the quest, decide if it's locked, completed, not started etc.

*How do i find the correct quest ID for the quest i look for ?* You can find all quests ID here : [Quest list](resources/quests_resources.md).

I think you guessed what we are gonna change ~~or maybe you didn't~~ wich is kinda self explanatory. This is **"status"** part.

Here are all available status for quests :
* Locked
* AvailableForStart
* Started
* AvailableForFinish
* Success
* Fail
* FailRestartable
* MarkedAsFailed

So, if you want to finish the quest you will need to change the status to : **"AvailableForFinish"**, but if you want to re-do a quest you already did, you will need to change the status to : **"AvailableForStart"**.

Don't forget to save your changes !



[Back at the top](tutorials/edit_the_player_profile.md#editing-differents-things-in-my-player-profile)
## Changing hideout areas status
Well, in this part you will learn how to change anything related to the hideout areas, that means, make it max level without having done the requirements for it.

For doing this heads to `ServerFolder/user/profiles/accountID/character.json` and search for this in the file : **"Hideout":**.

When found, you will see something like this, don't be scared ! :
```json
"Production": {},
		"Areas": [
			{
				"type": 3,
				"level": 4,
				"active": true,
				"passiveBonusesEnabled": true,
				"completeTime": 0,
				"constructing": false,
				"slots": []
			},
```
Let's explain what all this mean :
* **"Production":**
  * This is the list of all current productions in your hideout, scav cases, crafting meds etc...
* **"Areas":**
  * This is the list of all area of the hideout.
* **"type":**
  * This is the area ID for each specific thing in the hideout like *Scav case*, *Christmas tree*, *Stash*, *Workbench* etc...
* **"level":**
  * This is the level of the selected area.
* **"active":**
  * It define if the actual area is active or not.
* **"passiveBonusesEnabled":**
  * This define if the bonuses that the area should apply to the player are active or not.
* **"completeTime":**
  * The timestamp of when the constructions should be completed.
* **"constructing":**
  * Define if the area is actually under construction or not.
* **"slots":**
  * This list all objects stored by the area, mainly used for generators and bitcoin farm.

The two things that are important for us is : **"type":** and **"level":**. **Type** for knowning wich area we are editing and **Level** for setting it's level. You can find all area types and their max level here : [Hideout Areas list](resources/locations_resources.md)

The only thing you will have to do is changing the level to the max level number for selected area type and save your changes ! After that you can start your server and check your hideout !



[Back at the top](tutorials/edit_the_player_profile.md#editing-differents-things-in-my-player-profile)
## Editing traders
Well, in this part you will learn how to change your quest status, that means, make it finished without having done the requirements for it (you mainly need to do this when a specific quest is bugged)..

For doing this heads to `ServerFolder/user/profiles/accountID/character.json` and search for this in the file : **"TraderStandings":**.

You're going to face something like this when found : 
```json
"54cb50c76803fa8b248b4571": {
			"currentLevel": 1,
			"currentSalesSum": 368974,
			"currentStanding": 0.2,
			"NextLoyalty": null,
			"loyaltyLevels": {
				"0": {
					"minLevel": 1,
					"minSalesSum": 0,
					"minStanding": 0
				},
				"1": {
					"minLevel": 15,
					"minSalesSum": 1000000,
					"minStanding": 0.2
				},
				"2": {
					"minLevel": 22,
					"minSalesSum": 1500000,
					"minStanding": 0.35
				},
				"3": {
					"minLevel": 33,
					"minSalesSum": 2300000,
					"minStanding": 0.5
				}
			}
		},
```

Time to explain you everything !

* **"54cb50c76803fa8b248b4571":**
  * That's the trader ID.
* **"currentLevel":**
  * This is the current the trader is (yes it's kinda self explanatory).
* **"currentSalesSum":**
  * This is the total money you got for selling and buying to the trader.
* **"currentStanding":**
  * This is the total Standing points you got from quests for the trader.
* **"NextLoyalty":**
  * Don't pay attention to this.
* **"loyaltyLevels":**
  * This is all the Loyalty levels for the trader and their requirements.

So, for making all traders at their max loyalty level, we are going to take values from the Loyalty Level list, and take the last number values, and you will replace :
* **currentStanding** value by **minStanding** value.
* **currentSalesSum** value by **minSalesSum** value.
* Set **currentLevel** to **4**.

Only last thing is to save the changes ! And you're done, the trader is LL4 now. You can find the list of all traders ID here : [Traders ID List](resources/other_resources.md).

[Back at the top](tutorials/edit_the_player_profile.md#editing-differents-things-in-my-player-profile)


## Adding money to your character
In this part, we are going to add some cash in your inventory. For doing this we are going to make edits in the following file : `ServerFolder/user/profiles/accountID/character.json`.

First of all, make a stack of rouble, with a defined number, for an easier way, put it at **25666**, you now have a 25.666 stack of any money you choosed (can be lower number too, just make it a obvious number like 666 or 222 etc...). Now close the game **and** the server.

Open the file with VSCodium or Notepad++ and find the following line : **"StackObjectsCount": 25666** (for our exemple, but change the number with the stack you made).

This line is defining how much money the stack contain, and this is this line we are going to change. Now change the number **25666* by any number, like **99999999**. This will give you 99.999.999 $/€/Roubles

Save your changes and start the server, you now have a stack of 99.999.999 money !

[Back at the top](tutorials/edit_the_player_profile.md#editing-differents-things-in-my-player-profile)


# Thanks
**Tutorials made by : Sorata-Senpai**

# Official links
**Discord link**: https://discord.gg/3sR4KKS

**Reddit page**: https://www.reddit.com/r/EmuTarkov/