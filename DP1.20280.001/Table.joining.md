|Table 1|Table 2|Join by field Table 1|Join by field Table 2|
|------------------------|------------------------|-------------------------------|---------------------|
mmg_benthicDnaExtraction|mic_benthicDnaPooling|Not fully automatable: multiple subsampleIDs are pooled into each dnaSampleIDList||
mmg_benthicDnaExtraction|mmg\_benthicPcrAmplification\_16S|dnaSampleID|dnaSampleID|
mmg_benthicDnaExtraction|mmg\_benthicPcrAmplification\_ITS|dnaSampleID|dnaSampleID|
mic_benthicDnaPooling|mmg\_benthicPcrAmplification\_16S|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|mmg\_benthicPcrAmplification\_ITS|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|mmg\_benthicMarkerGeneSequencing\_16S|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|mmg\_benthicMarkerGeneSequencing\_ITS|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|mmg_benthicRawDataFiles|poolSampleID|dnaSampleID|
mic_benthicDnaPooling|amb_fieldParent|Requires intermediate table: join via mmg_benthicDnaExtraction||
mmg\_benthicPcrAmplification\_16S|mmg\_benthicMarkerGeneSequencing\_16S|dnaSampleID||
mmg\_benthicPcrAmplification\_ITS|mmg\_benthicMarkerGeneSequencing\_ITS|dnaSampleID||
mmg\_benthicMarkerGeneSequencing\_16S|mmg_benthicRawDataFiles|Not fully automatable: Filter the raw data table to only 16S samples, then join on dnaSampleID||
mmg\_benthicMarkerGeneSequencing\_ITS|mmg_benthicRawDataFiles|Not fully automatable: Filter the raw data table to only ITS samples, then join on dnaSampleID||
mmg_benthicDnaExtraction|amb_fieldParent|geneticSampleID|geneticSampleID|
amb_fieldParent|mmg\_benthicMarkerGeneSequencing\_16S|Requires intermediate table: join via mmg_benthicDnaExtraction and mic_benthicDnaPooling tables||
amb_fieldParent|mmg\_benthicMarkerGeneSequencing\_ITS|Requires intermediate table: join via mmg_benthicDnaExtraction and mic_benthicDnaPooling tables||
amb_fieldParent|mmg\_benthicPcrAmplification\_16S|Requires intermediate table: join via mmg_benthicDnaExtraction and mic_benthicDnaPooling tables||
amb_fieldParent|mmg\_benthicPcrAmplification\_ITS|Requires intermediate table: join via mmg_benthicDnaExtraction and mic_benthicDnaPooling tables||
amb_fieldParent|mmg_benthicRawDataFiles|Requires intermediate table: join via mmg_benthicDnaExtraction and mic_benthicDnaPooling tables||
mmg_benthicDnaExtraction|mmg\_benthicMarkerGeneSequencing\_16S|dnaSampleID|dnaSampleID|
mmg_benthicDnaExtraction|mmg\_benthicMarkerGeneSequencing\_ITS|dnaSampleID|dnaSampleID|
mmg_benthicDnaExtraction|mmg_benthicRawDataFiles|dnaSampleID|dnaSampleID|
mmg\_benthicMarkerGeneSequencing\_16S|mmg\_benthicMarkerGeneSequencing\_ITS|Join not recommended: different sequencing types||
mmg\_benthicMarkerGeneSequencing\_16S|mmg\_benthicPcrAmplification\_ITS|Join not recommended: different sequencing types||
mmg\_benthicMarkerGeneSequencing\_ITS|mmg\_benthicPcrAmplification\_16S|Join not recommended: different sequencing types||
mmg\_benthicPcrAmplification\_16S|mmg\_benthicPcrAmplification\_ITS|Join not recommended: different sequencing types||
mmg\_benthicPcrAmplification\_16S|mmg_benthicRawDataFiles|Not fully automatable: Filter the raw data table to only 16S samples, then join on dnaSampleID||
mmg\_benthicPcrAmplification\_ITS|mmg_benthicRawDataFiles|Not fully automatable: Filter the raw data table to only ITS samples, then join on dnaSampleID||
