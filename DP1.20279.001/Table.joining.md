|Table 1|Table 2|Join by field Table 1|Join by field Table 2|
|--------------------|--------------------|-------------------------|----------------|
amb_fieldParent|mms_benthicMetagenomeDnaExtraction|metagenomicsSampleID|genomicsSampleID|
mic_benthicDnaPooling|mms_benthicMetagenomeDnaExtraction|Not fully automatable: multiple subsampleIDs are pooled into each dnaSampleIDList||
mic_benthicDnaPooling|amb_fieldParent|Requires intermediate table: join via mms_benthicMetagenomeDnaExtraction||
mic_benthicDnaPooling|mms_benthicMetagenomeSequencing|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|mms_benthicRawDataFiles|poolSampleID|dnaSampleID|
mms_benthicMetagenomeDnaExtraction|mms_benthicMetagenomeSequencing|dnaSampleID|dnaSampleID|
mms_benthicMetagenomeSequencing|mms_benthicRawDataFiles|dnaSampleID|dnaSampleID|
amb_fieldParent|mms_benthicMetagenomeSequencing|Requires intermediate table: join via mms_benthicMetagenomeDnaExtraction||
amb_fieldParent|mms_benthicRawDataFiles|Requires intermediate table: join via mms_benthicMetagenomeDnaExtraction||
mms_benthicMetagenomeDnaExtraction|mms_benthicRawDataFiles|dnaSampleID|dnaSampleID|
