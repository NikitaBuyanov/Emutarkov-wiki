# Top
# Hideout areas

```
- AREA 0 : VENTS  | Max level : 3
- AREA 1 : SECURITY | Max level : 3
- AREA 2 : LAVATORY | Max level : 3
- AREA 3 : STASH | Max level : 4
- AREA 4 : GENERATOR | Max level : 3
- AREA 5 : HEATING | Max level : 3
- AREA 6 : WATER COLLECTOR | Max level : 3
- AREA 7 : MEDSTATION | Max level : 3
- AREA 8 : NUTRITION UNIT | Max level : 3
- AREA 9 : REST SPACE | Max level : 3
- AREA 10 : WORKBENCH | Max level : 3 
- AREA 11 : INTELLIGENCE CENTER | Max level : 3
- AREA 12 : SHOOTING RANGE | Max level : 1
- AREA 13 : LIBRARY | Max level : 1 
- AREA 14 : SCAV CASE | Max level : 1
- AREA 15 : ILLUMINATION | Max level : 3
- AREA 16 : PLACE OF FAME | Max level : 1
- AREA 17 : AIR FILTRERING UNIT | Max level : 1
- AREA 18 : SOLAR POWER | Max level : 1
- AREA 19 : BOOZE GENERATOR | Max level : 1
- AREA 20 : BITCOIN FARM | Max level : 3
- AREA 21 : CHRISTMAS TREE | Max level : 1
```

# HIDEOUT AREAS REQUIREMENTS TYPE
```
{
Area,
Item,
TraderUnlock,
TraderLoyalty,
Skill,
Resource
}
```

# LOCATION EXTRACTIONS REQUIREMENTS

```
{
None,
Empty,
TransferItem,
WorldEvent,
NotEmpty,
HasItem,
WearsItem,
EmptyOrSize,
SkillLevel,
Reference,
ScavCooperation,
Train
}
```

# LOCATION RULES
```
{
Normal,
AvoidOwnPmc,
AvoidAllPmc
}
```