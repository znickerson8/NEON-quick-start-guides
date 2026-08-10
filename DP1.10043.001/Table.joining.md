|Table 1|Table 2|Join by field(s)|
|------------------------|------------------------|-------------------------------|
mos_trapping|mos_sorting|sampleID
mos_sorting|mos_subsampling|Requires intermediate table: join via mos_expertTaxonomistID table (either Processed or Raw)
mos_trapping|mos_subsampling|Requires intermediate table: join via mos\_sorting table and mos\_expertTaxonomistID table (either Processed or Raw)
mos_sorting|mos_expertTaxonomistIDProcessed|subsampleID
mos_sorting|mos_expertTaxonomistIDRaw|subsampleID
mos_expertTaxonomistIDProcessed|mos_archivepooling|Requires intermediate table: join via mos_subsampling table
mos_expertTaxonomistIDRaw|mos_archivepooling|Requires intermediate table: join via mos_subsampling table
mos_archivepooling|mos_barcoding|Full join not recommended: tables not related
mos_archivepooling|mos_sorting|Requires intermediate table: join via mos\_sorting table and mos\_expertTaxonomistID table (either Processed or Raw) and mos\_subsampling table
mos_archivepooling|mos_subsampling|poolSampleID
mos_archivepooling|mos_trapping|Requires intermediate table: join via mos\_sorting and  mos\_expertTaxonomistID table (either Processed or Raw) and mos\_subsampling tables
mos_barcoding|mos_expertTaxonomistIDProcessed|Not fully automatable: multiple individualIDs pooled into each individualIDList
mos_barcoding|mos_expertTaxonomistIDRaw|Not fully automatable: multiple individualIDs pooled into each individualIDList
mos_barcoding|mos_sorting|Not fully automatable: multiple individualIDs pooled into each individualIDList
mos_barcoding|mos_subsampling|Not fully automatable: multiple individualIDs pooled into each individualIDList
mos_barcoding|mos_trapping|Not fully automatable: multiple individualIDs pooled into each individualIDList
mos_expertTaxonomistIDProcessed|mos_expertTaxonomistIDRaw|subsampleID,scientificName,sex
mos_expertTaxonomistIDProcessed|mos_subsampling|subsampleID,scientificName,sex
mos_expertTaxonomistIDProcessed|mos_trapping|Requires intermediate table: join via mos_sorting table
mos_expertTaxonomistIDRaw|mos_subsampling|subsampleID,scientificName,sex
mos_expertTaxonomistIDRaw|mos_trapping|Requires intermediate table: join via mos_sorting table
mos_identificationHistory|Any other table|Full join not recommended: Previous identifications of the same individual can be linked by identificationHistoryID in the mos\_expertTaxonomistID table (either Processed or Raw)
