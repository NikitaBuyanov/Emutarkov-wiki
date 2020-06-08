# Change some traders behaviour
## Requirements
For doing **any** edits in EmuTarkov i higly recommend you to use this software :
* [VSCodium](https://github.com/VSCodium/vscodium/releases)

This software is free and alot more helpfull for alot of things, like missing coma and everything about the syntax.
* Make a backup of the profile you're using.

For this, heads to `ServerFolder/db/assort/` choose the trader your want to modify ([Here's a list of each trader ID](resources/traders_ids.md)) and [create a mod](tutorials/create_a_mod) with the trader folder.

For all next tutorials, we will change only one trader, and always the same, this is *Prapor* and his ID is : **54cb50c76803fa8b248b4571**

**⚠️ If you want to make any changes, close both the game and the server, none of these should run ⚠️ .**

## Table :
* [Change traders avatars](tutorials/edit_traders_values.md#Change-traders-avatars)
* [Change insurance return time and max storage time](tutorials/edit_traders_values.md#Change-insurance-return-time-and-the-storage-time-in-mail)
* [Change repair quality and currency](tutorials/edit_traders_values.md#Change-repair-quality-and-currency)
* [Change traders Loyalty levels requirements](tutorials/edit_traders_values.md#Change-traders-LL-requirements)


## Change traders avatars
We will here learn how to change the return time of your insured items. For this heads to `/ServerFolder/user/mods/Author-YouModName-1.0.0/db/assort/54cb50c76803fa8b248b4571/base.json`.

And heads to this following line : **"avatar":**

This is defining the avatar path for the trader, you will need to add to your mod the new avatar your to use, for this, you can see [create a mod](tutorials/create_a_mod.md) tutorial. 

`"/files/trader/avatar/54cb50c76803fa8b248b4571.jpg"` files is defining the "res" folder, wich for us it's most likely /res/trader/avatar/id.jpg. So you need to put in your mod, a new folder at the same place as the **db** folder, called **res** and add the following path **trader/avatar/** into the **res** folder. Add your picture here, add it to your mod.config.json too and save the files ! You can use whatever name you want for the picture, you can replace the default one, or add a new one and change its path into base.json. You can now save all your files and start the server !


## Change insurance return time and the storage time in mail
We will here learn how to change the return time of your insured items. For this heads to `/ServerFolder/user/mods/Author-YouModName-1.0.0/db/assort/54cb50c76803fa8b248b4571/base.json`.

You need to search for this line : `"insurance":` and will face to this code :

```json
"insurance": {
		"availability": true,
		"min_payment": 0,
		"min_return_hour": 24,
		"max_return_hour": 36,
		"max_storage_time": 72,
		"excluded_category": []
	},
```

What does all this shit means ? Here we go, i tell you :
* **"availability":**
	* This define if the trader can insure your items or not.
* **"min_payment":**
	* This is actually not used.
* **"min_return_hour":**
	* This define the minimum time before an insured item to be sent you to your mail list.
* **"max_return_hour":**
	* This define the maximum time for an insured item to be sent you to your mail list.
* **"max_storage_time":**
	* This define how much time the mail will be available to be claim.
* **"excluded_category":**
	* This define wich items can't be insured to this trader.

So, what we want is to make the insured items to be sent immediatly after dying to your mail. For this we are going to change both **min_return_hour** and **max_return_hour** value to **0**.

And for being sure we wont loose them because we forgot to take the items from the mail, we will change **max_storage_time** value to **300**.

Note that values can't have decimals, because this is **hour** and 1.5 hour doesn't exist. The game will most likely get broke if you put a decimals in these values.

So no you can save your changes, remove all other unused files from your mods (aka all files except base.json) add the base.json to your mod.config.json, save and you can now restart the game ! At next raid, if you die, items will be imediatly sent back to your mail list.


[Back at the top](tutorials/edit_traders_values.md#Change-some-traders-behaviour)

## Change repair quality and currency
We will here learn how to change the return time of your insured items. For this heads to `/ServerFolder/user/mods/Author-YouModName-1.0.0/db/assort/54cb50c76803fa8b248b4571/base.json`.

You need to search for this line : `"repair":` and will face to this code :

```json
"repair": {
		"availability": true,
		"quality": "1.2",
		"excluded_id_list": [],
		"excluded_category": [],
		"currency": "5449016a4bdc2d6f028b456f",
		"currency_coefficient": 1,
		"price_rate": 0
	},
```
Again, i'm going to tell you each variables uses:
* **"availability":**
	* This define if the trader have the repair option available or not.
* **"quality":**
	* This define the quality of the repair. The lower the number is, better the armor will be repaired.
* **"excluded_id_list":**
	* This is a list of all excluded items that can't be repaired.
* **"excluded_category":**
	* This is a list of items cagetories that can't be repaired.
* **"currency":**
	* This define the actual currency to use for repairing.
* **"currency_coefficient":**
	* This is actually not used.
* **"price_rate":**
	* This is actually not used.

So we are going to make prapor repair the entire armor value and having to pay with dollars instead of roubles. For this we are going to modify these both values : **quality** and **currency**. We will change tha **quality** value by **0** to make it repair the entire armor points. As said in the explaination, the lower the number is, the better the armor will be repaired. If i increased this number, the armor would get less armors points when repairing.

And for changing the currency to dollars, we are going to change the value of **currency** variable by this one : **5696686a4bdc2da3298b456a** wich is the ID of dollar currency. You can find all currency ID's here : [Currency ID List](resources/traders_ids.md)

You can now save your file base.json, remove all unused files in your mods (so only keep base.json for this tutorial) add it to the mod.config.json and save !
You can now restart your server and see the changes in game !


[Back at the top](tutorials/edit_traders_values.md#Change-some-traders-behaviour)

## Change traders LL requirements
We will here learn how to change the return time of your insured items. For this heads to `/ServerFolder/user/mods/Author-YouModName-1.0.0/db/assort/54cb50c76803fa8b248b4571/base.json`.

You need to search for this line : `"loyalty":` and will face to this code :

```json
"loyalty": {
		"currentLevel": 1,
		"currentStanding": 0,
		"currentSalesSum": 0,
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
```
Let me explain you all these variables we get :
* **"currentLevel":**
	* This is the actual level the of the trader, it's not used by the server.
* **"currentStanding":**
	* This is the actual standing you have for this trader, it's not used by the server.
* **"currentSalesSum":**
	* This is the total of all purchased and sold items for this trader, it's not used by the server.
* **"loyaltyLevels":**
	* This define the list of all loyalty levels for the traders.
* **"0":**
	* This is the loyalty level (0 = LL1).
* **"minLevel":**
	* This is the minimum level requirements for the user to unlock this loyalty level.
* **"minSalesSum":**
	* This is the minimum amount of money spent in a trader to unlock this loyalty level.
* **"minStanding":**
	* This is the minimum standing you need to have with a trader to unlock this loyalty level.

For the exemple we will now increase the requirements for unlocking Prapor LL2. So heads to the **loyaltyLevels** **1**(as 0 = LL1, 1 = LL2), and let's increase the minimum level to 20 instead of 15. For this change the value of **"minLevel":** under **"1":** to 20. 

After increasing the minimum level, let's increase the standing requirement, so let's say we want the player to have 0.40 in standing with the trader to unlock the level. Look for **"minStanding":** and change its value to 0.4 instead of 0.2 (we are not forced to put 0.40 because if not specified, the server will read 0.40 even if you type 0.4).

We will now increase the minimum amount of cash the player spent into a trader. We want the player to have spent 4M500K roubles to prapor in order to get him to LL2. Let's change **"minSalesSum":** then and replace *1000000* by *4500000* and that's all ! We're good, you can now save your changes, remove all unused files in your mods (so only keep base.json for this tutorial) add it to the mod.config.json and save !

Restart your server and see the changes in game !


[Back at the top](tutorials/edit_traders_values.md#Change-some-traders-behaviour)

# Thanks
**Tutorials made by : Sorata-Senpai**

# Official links
**Discord link**: https://discord.gg/3sR4KKS

**Reddit page**: https://www.reddit.com/r/EmuTarkov/