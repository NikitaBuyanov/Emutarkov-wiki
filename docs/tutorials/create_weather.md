## STILL UNDER DEVELOPMENT
So yeah, information on this page is likely to change in the future

## Creating weather
1. Copy-paste a weather present from ```ServerDir/db/weather/```
2. Rename the weather present to what you want
3. Make changes where needed

We recommend you to add the weather as a mod. More info here : https://github.com/KandaSoranyan/JustEmuTarkovWiki/blob/master/tutorials/create_a_mod.md

## Editing weather
Note that the weather files are loaded only when the server starts. If you make changes to a weather profile during the game, restart the server for the changes to take into effect.

### ID's
id                         | description
-------------------------- | --------------------------------
wind_speed                 | wind speed
wind_direction             | wind direction
wind_gustiness             | wind gustiness
cloud                      | cloud density
fog                        | fog
rain                       | rain puddles intensity
rainIntensity              | falling rain intensity
temp                       | temperature
accelerate                 | weather change speed multiplier

### Ranges
id                         | min  | max
-------------------------- | ----  | ---
wind_speed                 | 0.0  | 1.0
wind_direction             | 1    | 8
wind_gustiness             | 0.0  | 1.0
cloud                      | -1.0 | 1.0
fog                        | 0.0  | 1
rain                       | 0    | 1	
rainIntensity              | 0    | 2
temp                       | -50  | 50
accelerate                 | 0    | 10

# Official links
**Discord link**: https://discord.gg/3sR4KKS

**Reddit page**: https://www.reddit.com/r/EmuTarkov/