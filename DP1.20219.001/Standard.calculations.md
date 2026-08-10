For quantitative results, follow these steps prior to analyzing data:
1. Join expert taxonomy and field data tables
```
    zoo_join <- neonOS::joinTableNEON(zoo_taxonomyProcessed, zoo_fieldData)
```
2. Calculate zooplankton abundance per liter
```
    zoo_join$abunPerL <- zoo_join$adjCountPerBottle / zoo_join$towsTrapsVolume
```
