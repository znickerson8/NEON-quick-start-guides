To calculate macroinvertebrate abundance per square meter, join the field and taxonomy tables using the instructions in the **Table joining** section of this document, or using the neonOS R package, then make the spatial calculation. To do this in the R language:

1. Join expert taxonomy and field data tables
```
inv_join <- neonOS::joinTableNEON(inv_taxonomyProcessed, inv_fieldData)
```

2. Calculate macroinvertebrate abundance per square meter
```
inv_join$abunPerM2 <- inv_join$estimatedTotalCount / inv_join$benthicArea
```
