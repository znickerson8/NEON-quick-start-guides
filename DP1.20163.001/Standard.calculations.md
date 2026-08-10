For phytoplankton and seston, use the following variables for concentration per L:
1. 2014-2023: alg_algaeExternalLabDataPerSample$analyteConcentration
2. 2024-present: alg_algaeDataPerSampleCompChl$analyteConcentration | alg_algaeDataPerSampleCompCNPS$analyteConcentration

For periphyton, follow this example code in R to calculate analyte concentrations per square meter:

2014-2023: alg_algaeExternalLabDataPerSample
1. Join external lab data and NEON domain lab data
```
alg_join1 <- neonOS::joinTableNEON(alg_algaeExternalLabDataPerSample, alg_domainLabChemistry)
```

2. Subset and join with field data to include the benthicArea
```
alg_fieldData_periphyton <- alg_fieldData %>%
  filter(algalSampleType != "phytoplankton" & algalSampleType != "seston")
alg_fieldData_subset <- alg_fieldData_periphyton[,c("parentSampleID", "benthicArea")] %>%
  distinct()
alg_join2 <- dplyr::left_join(alg_join1, alg_fieldData_subset,
  by = "parentSampleID")
```

3. Calculate analyte concentration per square meter
```
alg_join2$concentrationPerM2 <- alg_join2$analyteConcentration *
  (alg_join2$fieldSampleVolume / (alg_join2$benthicArea * 1000))
```

2024-present: alg_algaeDataPerSampleCompChl
1.  Join external lab chlorophyll data and NEON domain lab data, and filter to chlorophyll records
```
algCompCHL_join1 <- neonOS::joinTableNEON(alg_algaeDataPerSampleCompChl,
  alg_domainLabChemistryComp) 
algCompCHL_join1 <- algCompCHL_join1 %>%
  dplyr::filter(analysisType == "chlorophyll/pheophytin")
```

2. Subset and join with field data to include the benthicArea
```
alg_fieldData_periphyton <- alg_fieldData %>%
  filter(algalSampleType != "phytoplankton" & algalSampleType != "seston")
alg_fieldData_subset <- alg_fieldData_periphyton[,c("compositeSampleID", "benthicArea")] %>%
  distinct()
algCompCHL_join2 <- dplyr::left_join(algCompCHL_join1, alg_fieldData_subset,
  by = "compositeSampleID")
```

3. Calculate chlorophyll or pheophytin concentration per square meter
```
algCompCHL_join2$concentrationPerM2 <- algCompCHL_join2$analyteConcentration *
  (algCompCHL_join2$compositeFieldSampleVolume / (algCompCHL_join2$benthicArea * 1000))
```

2024-present: alg_algaeDataPerSampleCompCNPS
1.  Join external lab chlorophyll data and NEON domain lab data, and filter to C, N, P, or S records
```
algCompCNPS_join1 <- neonOS::joinTableNEON(alg_algaeDataPerSampleCompCNPS,
  alg_domainLabChemistryComp) 
algCompCNPS_join1 <- algCompCNPS_join1 %>%
  dplyr::filter(analysisType == "CNSa"| analysisType == "CNSb"| analysisType == "P")
```

2. Subset and join with field data to include the benthicArea
```
alg_fieldData_periphyton <- alg_fieldData %>%
  filter(algalSampleType != "phytoplankton" & algalSampleType != "seston")
alg_fieldData_subset <- alg_fieldData_periphyton[,c("compositeSampleID", "benthicArea")] %>%
  distinct()
algCompCNPS_join2 <- dplyr::left_join(algCompCNPS_join1, alg_fieldData_subset,
  by = "compositeSampleID")
```

3.  Calculate C, N, P, S, or isotope concentration per square meter
```
algCompCNPS_join2$concentrationPerM2 <- algCompCNPS_join2$analyteConcentration *
  (algCompCNPS_join2$compositeFieldSampleVolume / (algCompCNPS_join2$benthicArea * 1000))
```
