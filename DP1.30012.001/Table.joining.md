|Table 1|Table 2|Join by field(s)|
|------------------------|------------------------|-------------------------------|
fsp_boutMetadata|fsp_sampleMetadata|eventID
fsp_sampleMetadata|cfc_fieldData|sampleID
fsp_sampleMetadata|fsp_spectralData|spectralSampleID
fsp_boutMetadata|fsp_spectralData|Requires intermediate table: Join via fsp_sampleMetadata
fsp\_rawSpectra|Any other table|Join not recommended: spectralSampleID is the linking variable, but the fsp\_rawSpectra table contains data records for every wavelength measured. Note that this table will be named fsp\_rawSpectra when stacking data using the neonUtilities package; in downloads from data portal, these data will be presented in individual files named for the sample they describe.