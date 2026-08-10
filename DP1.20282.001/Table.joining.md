|Table 1|Table 2|Join by field Table 1|Join by field Table 2|
|------------------------|------------------------|-------------------------------|---------------------|
amc_fieldGenetic|mmg_swDnaExtraction|geneticSampleID||
mmg_swDnaExtraction|mic_swDnaPooling|Not fully automatable: multiple subsampleIDs are pooled into each dnaSampleIDList||
mic_swDnaPooling|mmg\_swPcrAmplification\_16S|poolSampleID|dnaSampleID|
mic_swDnaPooling|mmg\_swPcrAmplification\_ITS|poolSampleID|dnaSampleID|
mic_swDnaPooling|mmg\_swMarkerGeneSequencing\_16S|poolSampleID|dnaSampleID|
mic_swDnaPooling|mmg\_swMarkerGeneSequencing\_ITS|poolSampleID|dnaSampleID|
mic_swDnaPooling|mmg_swRawDataFiles|poolSampleID|dnaSampleID|
mic_swDnaPooling|amc_fieldGenetic|Requires intermediate table: join via mmg_swDnaExtraction table||
mic_swDnaPooling|amc_fieldSuperParent|Requires intermediate table: join via amc_fieldGenetic table||
mmg\_swPcrAmplification\_16S|mmg_swDnaExtraction|dnaSampleID|dnaSampleID|
mmg\_swPcrAmplification\_ITS|mmg_swDnaExtraction|dnaSampleID|dnaSampleID|
mmg\_swMarkerGeneSequencing\_16S|mmg\_swPcrAmplification\_16S|dnaSampleID|dnaSampleID|
mmg\_swMarkerGeneSequencing\_16S|mmg_swDnaExtraction|dnaSampleID|dnaSampleID|
mmg\_swMarkerGeneSequencing\_ITS|mmg\_swPcrAmplification\_ITS|dnaSampleID|dnaSampleID|
mmg\_swMarkerGeneSequencing\_ITS|mmg_swDnaExtraction|dnaSampleID|dnaSampleID|
mmg_swRawDataFiles|mmg_swPcrAmplification_ITS|dnaSampleID|dnaSampleID|
mmg_swRawDataFiles|mmg_swDnaExtraction|dnaSampleID|dnaSampleID|
amc_fieldGenetic|amc_fieldSuperParent|parentSampleID|parentSampleID|
amc_fieldGenetic|mmg\_swMarkerGeneSequencing\_16S|Requires intermediate table: join via mmg_swDnaExtraction table||
amc_fieldGenetic|mmg\_swMarkerGeneSequencing\_ITS|Requires intermediate table: join via mmg_swDnaExtraction table||
amc_fieldGenetic|mmg\_swPcrAmplification\_16S|Requires intermediate table: join via mmg_swDnaExtraction table||
amc_fieldGenetic|mmg\_swPcrAmplification\_ITS|Requires intermediate table: join via mmg_swDnaExtraction table||
amc_fieldGenetic|mmg_swRawDataFiles|Requires intermediate table: join via mmg_swDnaExtraction table||
amc_fieldSuperParent|mmg_swDnaExtraction|Requires intermediate table: join via amc_fieldGenetic table||
amc_fieldSuperParent|mmg\_swMarkerGeneSequencing\_16S|Requires intermediate table: join via amc\_fieldGenetic and mmg\_swDnaExtraction tables||
amc_fieldSuperParent|mmg\_swMarkerGeneSequencing\_ITS|Requires intermediate table: join via amc\_fieldGenetic and mmg\_swDnaExtraction tables||
amc_fieldSuperParent|mmg\_swPcrAmplification\_16S|Requires intermediate table: join via amc\_fieldGenetic and mmg\_swDnaExtraction tables||
amc_fieldSuperParent|mmg\_swPcrAmplification\_ITS|Requires intermediate table: join via amc\_fieldGenetic and mmg\_swDnaExtraction tables||
amc_fieldSuperParent|mmg_swRawDataFiles|Requires intermediate table: join via amc\_fieldGenetic and mmg\_swDnaExtraction tables||
mmg\_swMarkerGeneSequencing\_16S|mmg\_swMarkerGeneSequencing\_ITS|Join not recommended: different sequencing types||
mmg\_swMarkerGeneSequencing\_16S|mmg\_swPcrAmplification\_ITS|Join not recommended: different sequencing types||
mmg\_swMarkerGeneSequencing\_16S|mmg_swRawDataFiles|dnaSampleID|dnaSampleID|
mmg\_swMarkerGeneSequencing\_ITS|mmg\_swPcrAmplification\_16S|Join not recommended: different sequencing types||
mmg\_swMarkerGeneSequencing\_ITS|mmg_swRawDataFiles|dnaSampleID|dnaSampleID|
mmg\_swPcrAmplification\_16S|mmg\_swPcrAmplification\_ITS|Join not recommended: different sequencing types||
mmg\_swPcrAmplification\_16S|mmg_swRawDataFiles|dnaSampleID|dnaSampleID|
