|Table 1|Table 2|Join by field Table 1|Join by field Table 2|
|------------------------|------------------------|-------------------------------|-------------------------------|
alg_fieldData|alg_domainLabChemistry|parentSampleID|parentSampleID|
alg_algaeExternalLabDataPerSample|alg_domainLabChemistry|sampleID,sampleType,replicate|sampleID,analysisType,filterNumber|
alg_algaeExternalLabDataPerSample|alg_fieldData|Requires intermediate table: join via alg_domainLabChemistry table||
alg_algaeExternalLabDataPerSample|alg_algaeExternalLabQA|Join not recommended. Users interested in data quality can join by batchID, analyte, this will create a longer table that includes blanks and standards.||
alg_fieldData|alg_domainLabChemistryComp|compositeSampleID|compositeSampleID|
alg_algaeDataPerSampleCompChl|alg_domainLabChemistryComp|sampleID|analyteSampleID|
alg_algaeDataPerSampleCompCNPS|alg_domainLabChemistryComp|sampleID|analyteSampleID|
alg_algaeDataPerSampleCompChl|alg_algaeExternalLabQA|Join not recommended. Users interested in data quality can join by batchID, analyte, this will create a longer table that includes blanks and standards.||
alg_algaeDataPerSampleCompCNPS|alg_algaeExternalLabQA|Join not recommended. Users interested in data quality can join by batchID, analyte, this will create a longer table that includes blanks and standards.||
asi_externalLabPOMSummaryData|Any other table|Join not recommended. Quality control data can be connected to analyses by laboratoryName, analyte, and overlap of analysisDate with lab-specific start and end dates.||
