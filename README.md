# LIFE4137
Adaptation to Polyploidy Overlap among Arabidopsis and Cochlearia to Whole Genome Duplication
**Cochlearia**

**Arenosa**

| overlap among Arabidopsis and Cochlearia |           |           |
| ---------------------------------------- | --------- | --------- |
| AT4G10310                                | g40302.t1 | AL6G44160 |
| AT5G57110                                | g28609.t1 | AL8G33030 |
|                                          |           |           |
|                                          |           |           |

| overlap among Cardamine and Cochlearia |           |          |
| :------------------------------------: | :-------: | -------- |
|               AT4G23160                | g10577.t1 | CAg17768 |
|               AT2G09388                | g32048.t1 | CAg32248 |
|               AT3G42170                | g12208.t1 | CAg11103 |

**Cochlearia**

```shell
不用### g40302.t1
grep g40302.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g40302.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_2:4113454-4114535 Cexcelsa_scaf_2:4117100-4117330 Cexcelsa_scaf_2:4117593-4117809 > g40302.t1_reference.fasta
# create .dict file for g40302.t1 reference file
gatk CreateSequenceDictionary -R g40302.t1_reference.fasta -O g40302.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g40302.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_2:4108454-4122809
# g40302.t1 diploids consensus sequence
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_2:4113454-4114535 Cexcelsa_scaf_2:4117100-4117330 Cexcelsa_scaf_2:4117593-4117809 | bcftools consensus diplods_g40302.t1.vcf.gz -o diploids_g40302.t1.vcf.gz.fasta
# Applied 0 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g40302.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_2:4108454-4122809
# g40302.t1 diploids consensus sequence
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_2:4113454-4114535 Cexcelsa_scaf_2:4117100-4117330 Cexcelsa_scaf_2:4117593-4117809 | bcftools consensus tetraploid_g40302.t1.vcf.gz -o tetraploid_g40302.t1.vcf.gz.fasta
# Applied 0 variants
bcftools consensus -f g40302.t1_reference.fasta tetraploid_g40302.t1.vcf.gz -o tetraploid_g40302.t1.vcf.gz.fasta

```



```shell
#### g10577.t1
grep g10577.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g10577.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_1:3432326-3436300 Cexcelsa_scaf_1:3436373-3436406 Cexcelsa_scaf_1:3436660-3436961 > g10577.t1_reference.fasta
# create .dict file for g10577.t1 reference file
gatk CreateSequenceDictionary -R g10577.t1_reference.fasta -O g10577.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g10577.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_1:3431660-3441961
# g10577.t1 diploids consensus sequence
samtools faidx g10577.t1_reference.fasta Cexcelsa_scaf_1:3432326-3436300 Cexcelsa_scaf_1:3436373-3436406 Cexcelsa_scaf_1:3436660-3436961 | bcftools consensus diplods_g10577.t1.vcf.gz -o diploids_g10577.t1.vcf.gz.fasta
# Applied 1 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g10577.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_1:3431660-3441961
# g40302.t1 diploids consensus sequence
samtools faidx g10577.t1_reference.fasta Cexcelsa_scaf_1:3432326-3436300 Cexcelsa_scaf_1:3436373-3436406 Cexcelsa_scaf_1:3436660-3436961 | bcftools consensus tetraploid_g10577.t1.vcf.gz -o tetraploid_g10577.t1.vcf.gz.fasta
# Applied 37 variants
```

```shell
### g32048.t1
grep g32048.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g32048.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_3:4635253-4635906 Cexcelsa_scaf_3:4636492-4637578 Cexcelsa_scaf_3:4637632-4638242 > g32048.t1_reference.fasta
# create .dict file for g10577.t1 reference file
gatk CreateSequenceDictionary -R g32048.t1_reference.fasta -O g32048.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g32048.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_3:4632632-4643242
# g10577.t1 diploids consensus sequence
samtools faidx g32048.t1_reference.fasta Cexcelsa_scaf_3:4635253-4635906 Cexcelsa_scaf_3:4636492-4637578 Cexcelsa_scaf_3:4637632-4638242 | bcftools consensus diplods_g32048.t1.vcf.gz -o diploids_g32048.t1.vcf.gz.fasta
# Applied 0 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g32048.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_3:4632632-4643242
# g40302.t1 diploids consensus sequence
samtools faidx g32048.t1_reference.fasta Cexcelsa_scaf_3:4635253-4635906 Cexcelsa_scaf_3:4636492-4637578 Cexcelsa_scaf_3:4637632-4638242 | bcftools consensus tetraploid_g32048.t1.vcf.gz -o tetraploid_g32048.t1.vcf.gz.fasta
# Applied 2 variants
```



```shell
### g52921.t1
grep g52921.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g52921.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_6:18858391-18858398 Cexcelsa_scaf_6:18858492-18859300 Cexcelsa_scaf_6:18859404-18859490 Cexcelsa_scaf_6:18859699-18860181 Cexcelsa_scaf_6:18860438-18860466 > g52921.t1_reference.fasta
# create .dict file for g52921.t1 reference file
gatk CreateSequenceDictionary -R g52921.t1_reference.fasta -O g52921.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g52921.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_6:18853391-18865466
# g52921.t1 diploids consensus sequence
samtools faidx g52921.t1_reference.fasta Cexcelsa_scaf_6:18858391-18858398 Cexcelsa_scaf_6:18858492-18859300 Cexcelsa_scaf_6:18859404-18859490 Cexcelsa_scaf_6:18859699-18860181 Cexcelsa_scaf_6:18860438-18860466 | bcftools consensus diplods_g52921.t1.vcf.gz -o diploids_g52921.t1.vcf.gz.fasta
# Applied 1 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g52921.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_6:18853391-18865466
# g52921.t1 diploids consensus sequence
samtools faidx g52921.t1_reference.fasta Cexcelsa_scaf_6:18858391-18858398 Cexcelsa_scaf_6:18858492-18859300 Cexcelsa_scaf_6:18859404-18859490 Cexcelsa_scaf_6:18859699-18860181 Cexcelsa_scaf_6:18860438-18860466 | bcftools consensus tetraploid_g52921.t1.vcf.gz -o tetraploid_g52921.t1.vcf.gz.fasta
# Applied 3 variants
```



```shell
# delete X in protein sequence
echo "MGWVFPDSDTEVLGAERDHLNGAKSVRELYDIAXSNYTGKYTVPVLWDKKLKTIVNNESSEILRMFNTEFNHVAENPSLDLYPPNLRAIIDETNEWIHDEINNGVYKCGFAKNQETYDVAVKQLYDALDRCEEILRXQRFLCGNTLTEPDIRLFVTLIRFDEVLWDKKFKTIVNNESCQILRMFNTENPSLDLYPPNLRAIIDETNEWIHDGINNGVYKCGFAKNQETYDVAYAVIFKCDKRLVREYYNLFNYTKDIYQIAGMSSTVKMDHIKQNYYGSFPSLNPLEIIAPGPNIDYSLPHDRHRFSSESDYARLELLESASFVCEMSALLIEGSL" | tr -d 'X'

```

Arabidopsis and Cochlearia

```shell
### g2417.t1
grep g2417.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g2417.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_4:9959959-9960052 Cexcelsa_scaf_4:9960146-9960234 Cexcelsa_scaf_4:9960300-9960346 Cexcelsa_scaf_4:9960450-9960540 Cexcelsa_scaf_4:9960659-9960824 Cexcelsa_scaf_4:9961038-9961122 Cexcelsa_scaf_4:9961252-9961336 Cexcelsa_scaf_4:9961444-9961519 Cexcelsa_scaf_4:9961636-9961703 Cexcelsa_scaf_4:9961821-9961890 Cexcelsa_scaf_4:9962212-9962293 Cexcelsa_scaf_4:9962435-9962531 Cexcelsa_scaf_4:9962629-9962692 Cexcelsa_scaf_4:9962789-9962856 > g2417.t1_reference.fasta
# create .dict file for g2417.t1 reference file
gatk CreateSequenceDictionary -R g2417.t1_reference.fasta -O g2417.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g2417.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_4:9954959-9967856
# g2417.t1 diploids consensus sequence
samtools faidx g2417.t1_reference.fasta Cexcelsa_scaf_4:9959959-9960052 Cexcelsa_scaf_4:9960146-9960234 Cexcelsa_scaf_4:9960300-9960346 Cexcelsa_scaf_4:9960450-9960540 Cexcelsa_scaf_4:9960659-9960824 Cexcelsa_scaf_4:9961038-9961122 Cexcelsa_scaf_4:9961252-9961336 Cexcelsa_scaf_4:9961444-9961519 Cexcelsa_scaf_4:9961636-9961703 Cexcelsa_scaf_4:9961821-9961890 Cexcelsa_scaf_4:9962212-9962293 Cexcelsa_scaf_4:9962435-9962531 Cexcelsa_scaf_4:9962629-9962692 Cexcelsa_scaf_4:9962789-9962856 | bcftools consensus diplods_g2417.t1.vcf.gz -o diploids_g2417.t1.vcf.gz.fasta
# Applied 4 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g2417.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_4:9954959-9967856
# g2417.t1 diploids consensus sequence
samtools faidx g2417.t1_reference.fasta Cexcelsa_scaf_4:9959959-9960052 Cexcelsa_scaf_4:9960146-9960234 Cexcelsa_scaf_4:9960300-9960346 Cexcelsa_scaf_4:9960450-9960540 Cexcelsa_scaf_4:9960659-9960824 Cexcelsa_scaf_4:9961038-9961122 Cexcelsa_scaf_4:9961252-9961336 Cexcelsa_scaf_4:9961444-9961519 Cexcelsa_scaf_4:9961636-9961703 Cexcelsa_scaf_4:9961821-9961890 Cexcelsa_scaf_4:9962212-9962293 Cexcelsa_scaf_4:9962435-9962531 Cexcelsa_scaf_4:9962629-9962692 Cexcelsa_scaf_4:9962789-9962856 | bcftools consensus tetraploid_g2417.t1.vcf.gz -o tetraploid_g2417.t1.vcf.gz.fasta
# Applied 8 variants
```

```shell
### AL5G32850
1335-1525 2006-2090 2650-2740 2950-2977 3202-3301
scaffold_5:16011310-16011400 scaffold_5:16011981-16012065 scaffold_5:16012625-16012715 scaffold_5:16012925-16012952 scaffold_5:16013177-16013276
16009975-16013329

scaffold_5:16009975-16013329 scaffold_5:16014097-16016009 scaffold_5:20457986-20460309

grep AL5G32850 arenosa_cochlearia_overlapping_genes.gff
# create g2417.t1 reference fasta file
samtools faidx alygenomes.fasta scaffold_5:16011310-16011400 scaffold_5:16011981-16012065 scaffold_5:16012625-16012715 scaffold_5:16012925-16012952 scaffold_5:16013177-16013276 > AL5G32850_reference.fasta
# create .dict file for g2417.t1 reference file
gatk CreateSequenceDictionary -R AL5G32850_reference.fasta -O AL5G32850_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R alygenomes.fasta -V scaffold_5_genes.vcf.gz -O diplods_AL5G32850.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BEL_01da -sn BEL_02da -sn BEL_03da -sn BEL_04da -sn BEL_05da -sn BEL_06da -sn BEL_07da -sn BEL_08da -sn BIH_01da -sn BIH_02da -sn BIH_03da -sn BIH_04da -sn BIH_05da -sn BIH_06da -sn BIH_07da -sn BIH_08da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da -sn RZA_01da -sn RZA_02da -sn RZA_03da -sn RZA_04da -sn RZA_05da -sn RZA_06da -sn RZA_07da -sn RZA_08da -sn RZA_09da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn FOJ_01da -sn FOJ_02da -sn FOJ_03da -sn FOJ_04da -sn FOJ_05da -sn FOJ_06da -sn FOJ_07da -sn FOJ_08da -sn GOR_01da -sn GOR_02da -sn GOR_03da -sn GOR_04da -sn GOR_05da -sn GOR_06da -sn GOR_07da -sn GOR_08da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn SZI_01da -sn SZI_02da -sn SZI_03da -sn SZI_04da -sn SZI_05da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn HNI_01da -sn HNI_02da -sn HNI_03da -sn HNI_04da -sn KZL_01da -sn KZL_02da -sn KZL_03da -sn KZL_04da -sn KZL_05da -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn VEL_01da -sn VEL_02da -sn VEL_03da -sn VEL_04da -sn VEL_05da -sn VEL_06da -sn VEL_07da -sn VEL_08da -sn VEL_09da -sn VID_01da -sn VID_02da -sn VID_03da -sn VID_04da -sn VID_05da -sn VID_06da -sn VID_07da -sn VID_08da -sn MIE_02da -sn MIE_03da -sn MIE_04da -sn MIE_05da -sn MIE_06da -sn MIE_07da -sn MIE_08da -sn MIE_09da -sn MIE_10da	 -sn MIE_11da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da
# g2417.t1 diploids consensus sequence
samtools faidx alygenomes.fasta scaffold_5:16009975-16013329 | bcftools consensus diplods_AL5G32850.vcf.gz -o diploids_AL5G32850.vcf.gz.fasta
# Applied 16 variants


```

```shell
### g35052.t1
grep g35052.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g35052.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_3:25866514-25866909 > g35052.t1_reference.fasta
# create .dict file for g35052.t1 reference file
gatk CreateSequenceDictionary -R g35052.t1_reference.fasta -O g35052.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g35052.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_3:25861514-25871909
# g35052.t1 diploids consensus sequence
samtools faidx g35052.t1_reference.fasta Cexcelsa_scaf_3:25866514-25866909 | bcftools consensus diplods_g35052.t1.vcf.gz -o diploids_g35052.t1.vcf.gz.fasta
# Applied 0 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g35052.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_3:25861514-25871909
# g35052.t1 diploids consensus sequence
samtools faidx g35052.t1_reference.fasta Cexcelsa_scaf_3:25866514-25866909 | bcftools consensus tetraploid_g35052.t1.vcf.gz -o tetraploid_g35052.t1.vcf.gz.fasta
# Applied 1 variants
```

```shell
### g42057.t1
grep g42057.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g42057.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_2:11580867-11581183 Cexcelsa_scaf_2:11581549-11581769 Cexcelsa_scaf_2:11582040-11582062 > g42057.t1_reference.fasta
# create .dict file for g42057.t1 reference file
gatk CreateSequenceDictionary -R g42057.t1_reference.fasta -O g42057.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g42057.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_2:11575867-11587062
# g28609.t1 diploids consensus sequence
samtools faidx g42057.t1_reference.fasta Cexcelsa_scaf_2:11580867-11581183 Cexcelsa_scaf_2:11581549-11581769 Cexcelsa_scaf_2:11582040-11582062 | bcftools consensus diplods_g42057.t1.vcf.gz -o diploids_g42057.t1.vcf.gz.fasta


# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g42057.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_2:11575867-11587062
# g42057.t1 diploids consensus sequence
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_2:11580867-11581183 Cexcelsa_scaf_2:11581549-11581769 Cexcelsa_scaf_2:11582040-11582062 | bcftools consensus tetraploid_g42057.t1.vcf.gz -o tetraploid_g42057.t1.vcf.gz.fasta
# Applied 0 variants
```

```shell
不用### g54384.t1
grep g54384.t1 C_excelsa_V5_braker2_wRseq.gff3
# create g54384.t1 reference fasta file
samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_6:25813127-25813516 Cexcelsa_scaf_6:25813607-25813757 Cexcelsa_scaf_6:25813848-25814079 Cexcelsa_scaf_6:25814169-25814379 Cexcelsa_scaf_6:25814501-25814619 Cexcelsa_scaf_6:25814723-25814881 Cexcelsa_scaf_6:25814970-25815168 Cexcelsa_scaf_6:25815273-25815655 Cexcelsa_scaf_6:25815779-25815840 Cexcelsa_scaf_6:25815945-25815989 Cexcelsa_scaf_6:25816171-25816236 Cexcelsa_scaf_6:25816438-25816503 Cexcelsa_scaf_6:25816591-25816662 Cexcelsa_scaf_6:25816871-25816942 Cexcelsa_scaf_6:25817040-25817111 Cexcelsa_scaf_6:25817199-25817270 Cexcelsa_scaf_6:25817399-25817470 Cexcelsa_scaf_6:25817550-25817621 Cexcelsa_scaf_6:25817757-25817828 Cexcelsa_scaf_6:25817917-25817988 Cexcelsa_scaf_6:25818067-25818138 Cexcelsa_scaf_6:25818220-25818291 Cexcelsa_scaf_6:25818382-25818565 Cexcelsa_scaf_6:25818675-25818810 > g54384.t1_reference.fasta
# create .dict file for g54384.t1 reference file
gatk CreateSequenceDictionary -R g54384.t1_reference.fasta -O g54384.t1_reference.dict
# diploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g54384.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_6:25813675-25823810
# g54384.t1 diploids consensus sequence
samtools faidx g54384.t1_reference.fasta | bcftools consensus diplods_g54384.t1.vcf.gz -o diploids_g54384.t1.vcf.gz.fasta
## Applied 0 variants
bcftools consensus -f g54384.t1_reference.fasta diplods_g54384.t1.vcf.gz -o diploids_g54384.t1.vcf.gz.fasta
## Applied 5 variants

# tetraploids vcf file (around 5000bp)
gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g54384.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_6:25808127-25823810
# g54384.t1 diploids consensus sequence
samtools faidx g54384.t1_reference.fasta | bcftools consensus tetraploid_g54384.t1.vcf.gz -o tetraploid_g54384.t1.vcf.gz.fasta
# Applied 0 variants

bcftools consensus -f g54384.t1_reference.fasta tetraploid_g54384.t1.vcf.gz -o tetraploid_g54384.t1.vcf.gz.fasta
## Applied 13 variants
```

```shell
无变异### g6983.t1
grep g6983.t1 C_excelsa_V5_braker2_wRseq.gff3

samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_4:33366351-33366515 Cexcelsa_scaf_4:33366602-33366807 Cexcelsa_scaf_4:33366882-33367194 > g6983.t1_reference.fasta

gatk CreateSequenceDictionary -R g6983.t1_reference.fasta -O g6983.t1_reference.dict

gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g6983.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_4:33361351-33372194

samtools faidx g6983.t1_reference.fasta | bcftools consensus tetraploid_g6983.t1.vcf.gz -o tetraploid_g6983.t1.vcf.gz.fasta

bcftools consensus -f g6983.t1_reference.fasta tetraploid_g6983.t1.vcf.gz -o tetraploid_g6983.t1.vcf.gz.fasta
```

```shell
### g2416.t1
grep g2416.t1 C_excelsa_V5_braker2_wRseq.gff3

samtools faidx C_excelsa_V5.fasta Cexcelsa_scaf_4:9957177-9957242 Cexcelsa_scaf_4:9957310-9957371 Cexcelsa_scaf_4:9957706-9957934 Cexcelsa_scaf_4:9958294-9958402 Cexcelsa_scaf_4:9958629-9958759 Cexcelsa_scaf_4:9958861-9958929 Cexcelsa_scaf_4:9959031-9959177 Cexcelsa_scaf_4:9959261-9959368 > g2416.t1_reference.fasta

gatk CreateSequenceDictionary -R g2416.t1_reference.fasta -O g2416.t1_reference.dict

gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O diplods_g2416.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BNK_21 -sn CHA_1 -sn CHA_2 -sn JOR_1 -sn JOR_12 -sn JOR_13 -sn JOR_3 -sn LAB_004 -sn LAB_1 -sn LAB_2 -sn LAB_300 -sn LAB_4 -sn LAB_400 -sn LAB_5 -sn LAB_500 -sn NEN_001 -sn NEN_003 -sn NEN_200 -sn NEN_300 -sn NEN_4 -sn NEN_5 -sn NEN_6 -sn ODN_10 -sn ODN_2 -sn ODN_4 -sn ODN_5 -sn ODN_6 -sn ODN_7 -sn ODN_9 -sn RUZ_001 -sn SAL_003 -sn SAL_004 -sn SAL_006 -sn VEG_003 -sn VEG_004 -sn WOL_002 -sn WOL_006 -sn WOL_009 -sn WOL_010 -L Cexcelsa_scaf_4:9952177-9964368

bcftools consensus -f g2416.t1_reference.fasta diplods_g2416.t1.vcf.gz -o diploids_g2416.t1.vcf.gz.fasta
## Applied 0 variants

gatk SelectVariants -R C_excelsa_V5.fasta -V reheadered.F4_133.ann.vcf.gz -O tetraploid_g2416.t1.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn AAH_1 -sn AAH_2 -sn AAH_3 -sn AAH_4 -sn ALO_006 -sn ALO_007 -sn ALO_013 -sn ALO_017 -sn BEA_002 -sn BEA_004 -sn BEA_010 -sn BRI_002 -sn BRI_005 -sn BRI_006 -sn BRI_009 -sn ELI_001 -sn ELI_002 -sn ELI_003 -sn ELI_004 -sn ERS_1 -sn ERS_2 -sn ERS_3 -sn ERS_4 -sn FTW_1 -sn FTW_2 -sn FTW_3 -sn FTW_5 -sn GEO_2 -sn GEO_6 -sn KVA_002 -sn KVA_003 -sn KVA_009 -sn KVA_010 -sn LAL_1 -sn LAL_2 -sn LAL_3 -sn LAL_4 -sn LNL_001 -sn LNL_002 -sn LNL_003 -sn LNL_008 -sn LOS_1 -sn LOS_2 -sn LOS_6 -sn LOS_7 -sn MEL_001 -sn MEL_002 -sn NEI_1 -sn NEI_3 -sn NEI_8 -sn NEI_9 -sn ROT_004 -sn ROT_006 -sn ROT_007 -sn ROT_013 -sn SCU_14 -sn SCU_15 -sn SCU_16 -sn SCU_19 -sn SKI_004 -sn SKI_005 -sn SKN_001 -sn SKN_002 -sn SKN_005 -sn SKN_008 -sn TRO_001 -sn TRO_003 -sn TRO_005 -sn TRO_009 -sn VAG_003 -sn VAG_004 -sn VAG_007 -sn VAG_102 -L Cexcelsa_scaf_4:9952177-9964368

## samtools faidx g2416.t1_reference.fasta | bcftools consensus tetraploid_g2416.t1.vcf.gz -o tetraploid_g2416.t1.vcf.gz.fasta
bcftools consensus -f g2416.t1_reference.fasta tetraploid_g2416.t1.vcf.gz -o tetraploid_g2416.t1.vcf.gz.fasta
## Applied 5 variants

```



```shell
### AL1G64410
scaffold_1:2426006-2442689
scaffold_1:27147333-27160173
scaffold_1:29699695-29715956


IGV范围：scaffold_1:29702695-29712956
grep范围：scaffold_1:29704695-29710956

grep AL1G64410 arenosa_cochlearia_overlapping_genes.gff

samtools faidx alygenomes.fasta scaffold_1:29704695-29710956 > AL1G64410_reference.fasta

gatk CreateSequenceDictionary -R AL1G64410_reference.fasta -O AL1G64410_reference.dict
### diploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_1_genes.vcf.gz -O diplods_AL1G64410.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BEL_01da -sn BEL_02da -sn BEL_03da -sn BEL_04da -sn BEL_05da -sn BEL_06da -sn BEL_07da -sn BEL_08da -sn BIH_01da -sn BIH_02da -sn BIH_03da -sn BIH_04da -sn BIH_05da -sn BIH_06da -sn BIH_07da -sn BIH_08da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da -sn RZA_01da -sn RZA_02da -sn RZA_03da -sn RZA_04da -sn RZA_05da -sn RZA_06da -sn RZA_07da -sn RZA_08da -sn RZA_09da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn FOJ_01da -sn FOJ_02da -sn FOJ_03da -sn FOJ_04da -sn FOJ_05da -sn FOJ_06da -sn FOJ_07da -sn FOJ_08da -sn GOR_01da -sn GOR_02da -sn GOR_03da -sn GOR_04da -sn GOR_05da -sn GOR_06da -sn GOR_07da -sn GOR_08da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn SZI_01da -sn SZI_02da -sn SZI_03da -sn SZI_04da -sn SZI_05da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn HNI_01da -sn HNI_02da -sn HNI_03da -sn HNI_04da -sn KZL_01da -sn KZL_02da -sn KZL_03da -sn KZL_04da -sn KZL_05da -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn VEL_01da -sn VEL_02da -sn VEL_03da -sn VEL_04da -sn VEL_05da -sn VEL_06da -sn VEL_07da -sn VEL_08da -sn VEL_09da -sn VID_01da -sn VID_02da -sn VID_03da -sn VID_04da -sn VID_05da -sn VID_06da -sn VID_07da -sn VID_08da -sn MIE_02da -sn MIE_03da -sn MIE_04da -sn MIE_05da -sn MIE_06da -sn MIE_07da -sn MIE_08da -sn MIE_09da -sn MIE_10da	 -sn MIE_11da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da

bcftools consensus -f AL1G64410_reference.fasta diplods_AL1G64410.vcf.gz -o diploids_AL1G64410.vcf.gz.fasta
# Applied 72 variants

### tetraploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_1_genes.vcf.gz -O tetraploids_AL1G64410.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BGS_01ta -sn BGS_02ta -sn BGS_03ta -sn BGS_04ta -sn BGS_05ta -sn BGS_06ta -sn BGS_07ta -sn BGS_08ta -sn CHO_01ta -sn CHO_02ta -sn CHO_03ta -sn CHO_04ta -sn CHO_05ta -sn CHO_06ta -sn CHO_07ta -sn CHO_08ta -sn RFT_01ta -sn RFT_02ta -sn RFT_03ta -sn RFT_04ta -sn RFT_05ta -sn RFT_06ta -sn RFT_07ta -sn RFT_08ta -sn RFT_09ta -sn RFT_10ta -sn RFT_11ta -sn SCH_01ta -sn SCH_02ta -sn SCH_03ta -sn SCH_04ta -sn SCH_05ta -sn SCH_06ta -sn SCH_07ta -sn DRA_01ta -sn DRA_02ta -sn DRA_03ta -sn DRA_04ta -sn DRA_05ta -sn DRA_06ta -sn DRA_07ta -sn DRA_08ta -sn GUL_01ta -sn GUL_02ta -sn GUL_03ta -sn GUL_04ta -sn GUL_05ta -sn GUL_06ta -sn GUL_07ta -sn GUL_08ta -sn GUL_09ta -sn GUL_10ta -sn GUL_11ta -sn GUL_12ta -sn GUL_13ta -sn GUL_14ta -sn GUL_15ta -sn GUL_16ta -sn GUL_17ta -sn GUL_18ta -sn GUL_19ta -sn HAR_01ta -sn HAR_02ta -sn SPI_01ta -sn SPI_02ta -sn SPI_03ta -sn SPI_04ta -sn SPI_05ta -sn SPI_06ta -sn SPI_07ta -sn SPI_08ta -sn SPI_09ta -sn SPI_10ta -sn SPI_11ta -sn SPI_12ta -sn SPI_13ta -sn STE_01ta -sn STE_02ta -sn STE_03ta -sn STE_04ta -sn STE_05ta -sn STE_06ta -sn STE_07ta -sn STE_08ta -sn SWA_01ta -sn SWA_02ta -sn SWA_03ta -sn SWA_04ta -sn SWA_05ta -sn SWA_06ta -sn SWA_07ta -sn SWA_08ta -sn SWA_09ta -sn SWA_10ta -sn TBG_01ta -sn TBG_02ta -sn TBG_03ta -sn TBG_04ta -sn TBG_05ta -sn TBG_06ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn HOC_01ta -sn HOC_02ta -sn HOC_03ta -sn HOC_04ta -sn HOC_05ta -sn HOC_06ta -sn HOC_07ta -sn HOC_08ta -sn KAS_01ta -sn KAS_02ta -sn KAS_03ta -sn KAS_04ta -sn KAS_05ta -sn KAS_06ta -sn KAS_07ta -sn KAS_08ta -sn KOS_01ta -sn KOS_02ta -sn KOS_03ta -sn KOS_04ta -sn KOS_05ta -sn KOS_06ta -sn KOS_07ta -sn KOW_02ta -sn KOW_03ta -sn KOW_04ta -sn KOW_05ta -sn KOW_06ta -sn KOW_07ta -sn KOW_08ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn TRT_01ta -sn TRT_02ta -sn TRT_03ta -sn TRT_04ta -sn TRT_05ta -sn TRT_06ta -sn TRT_07ta -sn TRT_08ta -sn TRT_09ta -sn TZI_01ta -sn TZI_02ta -sn TZI_03ta -sn TZI_04ta -sn TZI_05ta -sn TZI_06ta -sn TZI_07ta -sn TZI_08ta -sn TZI_09ta -sn TZI_10ta -sn LAC_01ta -sn LAC_02ta -sn LAC_03ta -sn LAC_04ta -sn LAC_05ta -sn LAC_06ta -sn LAC_07ta -sn LAC_08ta -sn WEK_01ta -sn WEK_02ta -sn WEK_03ta -sn WEK_04ta -sn WEK_05ta -sn WEK_06ta -sn WEK_07ta -sn WEK_08ta -sn ZAP_01ta -sn ZAP_02ta -sn ZAP_03ta -sn ZAP_04ta -sn ZAP_05ta -sn ZAP_06ta -sn ZAP_07ta -sn ZAP_08ta

bcftools consensus -f AL1G64410_reference.fasta tetraploids_AL1G64410.vcf.gz -o tetraploids_AL1G64410.vcf.gz.fasta
## Applied 63 variants

```

```shell
	### 提取内含子
	gtf2bed < arenosa_cochlearia_overlapping_genes.gff > output.bed
	
	awk '$3 == "exon"' arenosa_cochlearia_overlapping_genes.gff > exons.gtf
	
	
	
	arenosa_cochlearia_overlapping_genes.gff.gz
	zcat arenosa_cochlearia_overlapping_genes.gff.gz | awk '$3 == "exon" && $9 ~ /ID=AL1G64410/ {print $1, $4-1, $5}' | sort -k1,1 -k2,2n > AL1G64410_exons.bed
    
    
  zcat arenosa_cochlearia_overlapping_genes.gff.gz | awk 'BEGIN{OFS="\t";} $3=="exon" {print $1,$4-1,$5}' | sort -k1,1 -k2,2n| bedtools merge > exon.sort.bedtools.merge.bed
```

```shell
grep AL5G32850 arenosa_cochlearia_overlapping_genes.gff

samtools faidx alygenomes.fasta scaffold_5:16009975-16013329 > AL5G32850_reference.fasta

gatk CreateSequenceDictionary -R AL1G64410_reference.fasta -O AL5G32850_reference.dict
### diploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_5_genes.vcf.gz -O diplods_AL5G32850.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BEL_01da -sn BEL_02da -sn BEL_03da -sn BEL_04da -sn BEL_05da -sn BEL_06da -sn BEL_07da -sn BEL_08da -sn BIH_01da -sn BIH_02da -sn BIH_03da -sn BIH_04da -sn BIH_05da -sn BIH_06da -sn BIH_07da -sn BIH_08da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da -sn RZA_01da -sn RZA_02da -sn RZA_03da -sn RZA_04da -sn RZA_05da -sn RZA_06da -sn RZA_07da -sn RZA_08da -sn RZA_09da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn FOJ_01da -sn FOJ_02da -sn FOJ_03da -sn FOJ_04da -sn FOJ_05da -sn FOJ_06da -sn FOJ_07da -sn FOJ_08da -sn GOR_01da -sn GOR_02da -sn GOR_03da -sn GOR_04da -sn GOR_05da -sn GOR_06da -sn GOR_07da -sn GOR_08da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn SZI_01da -sn SZI_02da -sn SZI_03da -sn SZI_04da -sn SZI_05da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn HNI_01da -sn HNI_02da -sn HNI_03da -sn HNI_04da -sn KZL_01da -sn KZL_02da -sn KZL_03da -sn KZL_04da -sn KZL_05da -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn VEL_01da -sn VEL_02da -sn VEL_03da -sn VEL_04da -sn VEL_05da -sn VEL_06da -sn VEL_07da -sn VEL_08da -sn VEL_09da -sn VID_01da -sn VID_02da -sn VID_03da -sn VID_04da -sn VID_05da -sn VID_06da -sn VID_07da -sn VID_08da -sn MIE_02da -sn MIE_03da -sn MIE_04da -sn MIE_05da -sn MIE_06da -sn MIE_07da -sn MIE_08da -sn MIE_09da -sn MIE_10da	 -sn MIE_11da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da

bcftools consensus -f AL5G32850_reference.fasta diplods_AL5G32850.vcf.gz -o diploids_AL5G32850.vcf.gz.fasta
# Applied 16 variants

### tetraploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_5_genes.vcf.gz -O tetraploids_AL5G32850.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BGS_01ta -sn BGS_02ta -sn BGS_03ta -sn BGS_04ta -sn BGS_05ta -sn BGS_06ta -sn BGS_07ta -sn BGS_08ta -sn CHO_01ta -sn CHO_02ta -sn CHO_03ta -sn CHO_04ta -sn CHO_05ta -sn CHO_06ta -sn CHO_07ta -sn CHO_08ta -sn RFT_01ta -sn RFT_02ta -sn RFT_03ta -sn RFT_04ta -sn RFT_05ta -sn RFT_06ta -sn RFT_07ta -sn RFT_08ta -sn RFT_09ta -sn RFT_10ta -sn RFT_11ta -sn SCH_01ta -sn SCH_02ta -sn SCH_03ta -sn SCH_04ta -sn SCH_05ta -sn SCH_06ta -sn SCH_07ta -sn DRA_01ta -sn DRA_02ta -sn DRA_03ta -sn DRA_04ta -sn DRA_05ta -sn DRA_06ta -sn DRA_07ta -sn DRA_08ta -sn GUL_01ta -sn GUL_02ta -sn GUL_03ta -sn GUL_04ta -sn GUL_05ta -sn GUL_06ta -sn GUL_07ta -sn GUL_08ta -sn GUL_09ta -sn GUL_10ta -sn GUL_11ta -sn GUL_12ta -sn GUL_13ta -sn GUL_14ta -sn GUL_15ta -sn GUL_16ta -sn GUL_17ta -sn GUL_18ta -sn GUL_19ta -sn HAR_01ta -sn HAR_02ta -sn SPI_01ta -sn SPI_02ta -sn SPI_03ta -sn SPI_04ta -sn SPI_05ta -sn SPI_06ta -sn SPI_07ta -sn SPI_08ta -sn SPI_09ta -sn SPI_10ta -sn SPI_11ta -sn SPI_12ta -sn SPI_13ta -sn STE_01ta -sn STE_02ta -sn STE_03ta -sn STE_04ta -sn STE_05ta -sn STE_06ta -sn STE_07ta -sn STE_08ta -sn SWA_01ta -sn SWA_02ta -sn SWA_03ta -sn SWA_04ta -sn SWA_05ta -sn SWA_06ta -sn SWA_07ta -sn SWA_08ta -sn SWA_09ta -sn SWA_10ta -sn TBG_01ta -sn TBG_02ta -sn TBG_03ta -sn TBG_04ta -sn TBG_05ta -sn TBG_06ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn HOC_01ta -sn HOC_02ta -sn HOC_03ta -sn HOC_04ta -sn HOC_05ta -sn HOC_06ta -sn HOC_07ta -sn HOC_08ta -sn KAS_01ta -sn KAS_02ta -sn KAS_03ta -sn KAS_04ta -sn KAS_05ta -sn KAS_06ta -sn KAS_07ta -sn KAS_08ta -sn KOS_01ta -sn KOS_02ta -sn KOS_03ta -sn KOS_04ta -sn KOS_05ta -sn KOS_06ta -sn KOS_07ta -sn KOW_02ta -sn KOW_03ta -sn KOW_04ta -sn KOW_05ta -sn KOW_06ta -sn KOW_07ta -sn KOW_08ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn TRT_01ta -sn TRT_02ta -sn TRT_03ta -sn TRT_04ta -sn TRT_05ta -sn TRT_06ta -sn TRT_07ta -sn TRT_08ta -sn TRT_09ta -sn TZI_01ta -sn TZI_02ta -sn TZI_03ta -sn TZI_04ta -sn TZI_05ta -sn TZI_06ta -sn TZI_07ta -sn TZI_08ta -sn TZI_09ta -sn TZI_10ta -sn LAC_01ta -sn LAC_02ta -sn LAC_03ta -sn LAC_04ta -sn LAC_05ta -sn LAC_06ta -sn LAC_07ta -sn LAC_08ta -sn WEK_01ta -sn WEK_02ta -sn WEK_03ta -sn WEK_04ta -sn WEK_05ta -sn WEK_06ta -sn WEK_07ta -sn WEK_08ta -sn ZAP_01ta -sn ZAP_02ta -sn ZAP_03ta -sn ZAP_04ta -sn ZAP_05ta -sn ZAP_06ta -sn ZAP_07ta -sn ZAP_08ta

bcftools consensus -f AL5G32850_reference.fasta tetraploids_AL5G32850.vcf.gz -o tetraploids_AL5G32850.vcf.gz.fasta
# Applied 16 variants
```



```shell
## AL5G32860

grep AL5G32860 arenosa_cochlearia_overlapping_genes.gff

samtools faidx alygenomes.fasta scaffold_5:16014097-16016009 > AL5G32860_reference.fasta

gatk CreateSequenceDictionary -R AL5G32860_reference.fasta -O AL5G32860_reference.dict

### diploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_5_genes.vcf.gz -O diplods_AL5G32860.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BEL_01da -sn BEL_02da -sn BEL_03da -sn BEL_04da -sn BEL_05da -sn BEL_06da -sn BEL_07da -sn BEL_08da -sn BIH_01da -sn BIH_02da -sn BIH_03da -sn BIH_04da -sn BIH_05da -sn BIH_06da -sn BIH_07da -sn BIH_08da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da -sn RZA_01da -sn RZA_02da -sn RZA_03da -sn RZA_04da -sn RZA_05da -sn RZA_06da -sn RZA_07da -sn RZA_08da -sn RZA_09da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn FOJ_01da -sn FOJ_02da -sn FOJ_03da -sn FOJ_04da -sn FOJ_05da -sn FOJ_06da -sn FOJ_07da -sn FOJ_08da -sn GOR_01da -sn GOR_02da -sn GOR_03da -sn GOR_04da -sn GOR_05da -sn GOR_06da -sn GOR_07da -sn GOR_08da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn SZI_01da -sn SZI_02da -sn SZI_03da -sn SZI_04da -sn SZI_05da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn HNI_01da -sn HNI_02da -sn HNI_03da -sn HNI_04da -sn KZL_01da -sn KZL_02da -sn KZL_03da -sn KZL_04da -sn KZL_05da -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn VEL_01da -sn VEL_02da -sn VEL_03da -sn VEL_04da -sn VEL_05da -sn VEL_06da -sn VEL_07da -sn VEL_08da -sn VEL_09da -sn VID_01da -sn VID_02da -sn VID_03da -sn VID_04da -sn VID_05da -sn VID_06da -sn VID_07da -sn VID_08da -sn MIE_02da -sn MIE_03da -sn MIE_04da -sn MIE_05da -sn MIE_06da -sn MIE_07da -sn MIE_08da -sn MIE_09da -sn MIE_10da	 -sn MIE_11da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da

bcftools consensus -f AL5G32860_reference.fasta diplods_AL5G32860.vcf.gz -o diploids_AL5G.vcf.gz.fasta
## Applied 16 variants
### tetraploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_5_genes.vcf.gz -O tetraploids_AL5G32860.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BGS_01ta -sn BGS_02ta -sn BGS_03ta -sn BGS_04ta -sn BGS_05ta -sn BGS_06ta -sn BGS_07ta -sn BGS_08ta -sn CHO_01ta -sn CHO_02ta -sn CHO_03ta -sn CHO_04ta -sn CHO_05ta -sn CHO_06ta -sn CHO_07ta -sn CHO_08ta -sn RFT_01ta -sn RFT_02ta -sn RFT_03ta -sn RFT_04ta -sn RFT_05ta -sn RFT_06ta -sn RFT_07ta -sn RFT_08ta -sn RFT_09ta -sn RFT_10ta -sn RFT_11ta -sn SCH_01ta -sn SCH_02ta -sn SCH_03ta -sn SCH_04ta -sn SCH_05ta -sn SCH_06ta -sn SCH_07ta -sn DRA_01ta -sn DRA_02ta -sn DRA_03ta -sn DRA_04ta -sn DRA_05ta -sn DRA_06ta -sn DRA_07ta -sn DRA_08ta -sn GUL_01ta -sn GUL_02ta -sn GUL_03ta -sn GUL_04ta -sn GUL_05ta -sn GUL_06ta -sn GUL_07ta -sn GUL_08ta -sn GUL_09ta -sn GUL_10ta -sn GUL_11ta -sn GUL_12ta -sn GUL_13ta -sn GUL_14ta -sn GUL_15ta -sn GUL_16ta -sn GUL_17ta -sn GUL_18ta -sn GUL_19ta -sn HAR_01ta -sn HAR_02ta -sn SPI_01ta -sn SPI_02ta -sn SPI_03ta -sn SPI_04ta -sn SPI_05ta -sn SPI_06ta -sn SPI_07ta -sn SPI_08ta -sn SPI_09ta -sn SPI_10ta -sn SPI_11ta -sn SPI_12ta -sn SPI_13ta -sn STE_01ta -sn STE_02ta -sn STE_03ta -sn STE_04ta -sn STE_05ta -sn STE_06ta -sn STE_07ta -sn STE_08ta -sn SWA_01ta -sn SWA_02ta -sn SWA_03ta -sn SWA_04ta -sn SWA_05ta -sn SWA_06ta -sn SWA_07ta -sn SWA_08ta -sn SWA_09ta -sn SWA_10ta -sn TBG_01ta -sn TBG_02ta -sn TBG_03ta -sn TBG_04ta -sn TBG_05ta -sn TBG_06ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn HOC_01ta -sn HOC_02ta -sn HOC_03ta -sn HOC_04ta -sn HOC_05ta -sn HOC_06ta -sn HOC_07ta -sn HOC_08ta -sn KAS_01ta -sn KAS_02ta -sn KAS_03ta -sn KAS_04ta -sn KAS_05ta -sn KAS_06ta -sn KAS_07ta -sn KAS_08ta -sn KOS_01ta -sn KOS_02ta -sn KOS_03ta -sn KOS_04ta -sn KOS_05ta -sn KOS_06ta -sn KOS_07ta -sn KOW_02ta -sn KOW_03ta -sn KOW_04ta -sn KOW_05ta -sn KOW_06ta -sn KOW_07ta -sn KOW_08ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn TRT_01ta -sn TRT_02ta -sn TRT_03ta -sn TRT_04ta -sn TRT_05ta -sn TRT_06ta -sn TRT_07ta -sn TRT_08ta -sn TRT_09ta -sn TZI_01ta -sn TZI_02ta -sn TZI_03ta -sn TZI_04ta -sn TZI_05ta -sn TZI_06ta -sn TZI_07ta -sn TZI_08ta -sn TZI_09ta -sn TZI_10ta -sn LAC_01ta -sn LAC_02ta -sn LAC_03ta -sn LAC_04ta -sn LAC_05ta -sn LAC_06ta -sn LAC_07ta -sn LAC_08ta -sn WEK_01ta -sn WEK_02ta -sn WEK_03ta -sn WEK_04ta -sn WEK_05ta -sn WEK_06ta -sn WEK_07ta -sn WEK_08ta -sn ZAP_01ta -sn ZAP_02ta -sn ZAP_03ta -sn ZAP_04ta -sn ZAP_05ta -sn ZAP_06ta -sn ZAP_07ta -sn ZAP_08ta

bcftools consensus -f AL5G32860_reference.fasta tetraploids_AL5G32860.vcf.gz -o tetraploids_AL5G32860.vcf.gz.fasta
# Applied 27 variants
```

```shell
### AL8G14450
grep AL8G14450 arenosa_cochlearia_overlapping_genes.gff

samtools faidx alygenomes.fasta scaffold_8:2785543-2789170 > AL8G14450_reference.fasta

gatk CreateSequenceDictionary -R AL8G14450_reference.fasta -O AL8G14450_reference.dict

### diploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_8_genes.vcf.gz -O diplods_AL8G14450.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BEL_01da -sn BEL_02da -sn BEL_03da -sn BEL_04da -sn BEL_05da -sn BEL_06da -sn BEL_07da -sn BEL_08da -sn BIH_01da -sn BIH_02da -sn BIH_03da -sn BIH_04da -sn BIH_05da -sn BIH_06da -sn BIH_07da -sn BIH_08da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da -sn RZA_01da -sn RZA_02da -sn RZA_03da -sn RZA_04da -sn RZA_05da -sn RZA_06da -sn RZA_07da -sn RZA_08da -sn RZA_09da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn FOJ_01da -sn FOJ_02da -sn FOJ_03da -sn FOJ_04da -sn FOJ_05da -sn FOJ_06da -sn FOJ_07da -sn FOJ_08da -sn GOR_01da -sn GOR_02da -sn GOR_03da -sn GOR_04da -sn GOR_05da -sn GOR_06da -sn GOR_07da -sn GOR_08da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn SNO_01da -sn SNO_02da -sn SNO_03da -sn SNO_04da -sn SNO_05da -sn SNO_06da -sn SZI_01da -sn SZI_02da -sn SZI_03da -sn SZI_04da -sn SZI_05da -sn HNE_01da -sn HNE_02da -sn HNE_03da -sn HNE_04da -sn HNE_05da -sn HNE_06da -sn HNE_07da -sn HNI_01da -sn HNI_02da -sn HNI_03da -sn HNI_04da -sn KZL_01da -sn KZL_02da -sn KZL_03da -sn KZL_04da -sn KZL_05da -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn VEL_01da -sn VEL_02da -sn VEL_03da -sn VEL_04da -sn VEL_05da -sn VEL_06da -sn VEL_07da -sn VEL_08da -sn VEL_09da -sn VID_01da -sn VID_02da -sn VID_03da -sn VID_04da -sn VID_05da -sn VID_06da -sn VID_07da -sn VID_08da -sn MIE_02da -sn MIE_03da -sn MIE_04da -sn MIE_05da -sn MIE_06da -sn MIE_07da -sn MIE_08da -sn MIE_09da -sn MIE_10da	 -sn MIE_11da -sn PRE_01da -sn PRE_02da -sn PRE_03da -sn PRE_04da -sn PRE_05da -sn PRE_06da -sn PRE_07da -sn PRE_08da

bcftools consensus -f AL8G14450_reference.fasta diplods_AL8G14450.vcf.gz -o diploids_AL8G14450.vcf.gz.fasta
# Applied 5 variants

### tetraploids
gatk SelectVariants -R alygenomes.fasta -V scaffold_8_genes.vcf.gz -O tetraploids_AL8G14450.vcf.gz --restrict-alleles-to BIALLELIC -select "AF>0.5" -sn BGS_01ta -sn BGS_02ta -sn BGS_03ta -sn BGS_04ta -sn BGS_05ta -sn BGS_06ta -sn BGS_07ta -sn BGS_08ta -sn CHO_01ta -sn CHO_02ta -sn CHO_03ta -sn CHO_04ta -sn CHO_05ta -sn CHO_06ta -sn CHO_07ta -sn CHO_08ta -sn RFT_01ta -sn RFT_02ta -sn RFT_03ta -sn RFT_04ta -sn RFT_05ta -sn RFT_06ta -sn RFT_07ta -sn RFT_08ta -sn RFT_09ta -sn RFT_10ta -sn RFT_11ta -sn SCH_01ta -sn SCH_02ta -sn SCH_03ta -sn SCH_04ta -sn SCH_05ta -sn SCH_06ta -sn SCH_07ta -sn DRA_01ta -sn DRA_02ta -sn DRA_03ta -sn DRA_04ta -sn DRA_05ta -sn DRA_06ta -sn DRA_07ta -sn DRA_08ta -sn GUL_01ta -sn GUL_02ta -sn GUL_03ta -sn GUL_04ta -sn GUL_05ta -sn GUL_06ta -sn GUL_07ta -sn GUL_08ta -sn GUL_09ta -sn GUL_10ta -sn GUL_11ta -sn GUL_12ta -sn GUL_13ta -sn GUL_14ta -sn GUL_15ta -sn GUL_16ta -sn GUL_17ta -sn GUL_18ta -sn GUL_19ta -sn HAR_01ta -sn HAR_02ta -sn SPI_01ta -sn SPI_02ta -sn SPI_03ta -sn SPI_04ta -sn SPI_05ta -sn SPI_06ta -sn SPI_07ta -sn SPI_08ta -sn SPI_09ta -sn SPI_10ta -sn SPI_11ta -sn SPI_12ta -sn SPI_13ta -sn STE_01ta -sn STE_02ta -sn STE_03ta -sn STE_04ta -sn STE_05ta -sn STE_06ta -sn STE_07ta -sn STE_08ta -sn SWA_01ta -sn SWA_02ta -sn SWA_03ta -sn SWA_04ta -sn SWA_05ta -sn SWA_06ta -sn SWA_07ta -sn SWA_08ta -sn SWA_09ta -sn SWA_10ta -sn TBG_01ta -sn TBG_02ta -sn TBG_03ta -sn TBG_04ta -sn TBG_05ta -sn TBG_06ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn HOC_01ta -sn HOC_02ta -sn HOC_03ta -sn HOC_04ta -sn HOC_05ta -sn HOC_06ta -sn HOC_07ta -sn HOC_08ta -sn KAS_01ta -sn KAS_02ta -sn KAS_03ta -sn KAS_04ta -sn KAS_05ta -sn KAS_06ta -sn KAS_07ta -sn KAS_08ta -sn KOS_01ta -sn KOS_02ta -sn KOS_03ta -sn KOS_04ta -sn KOS_05ta -sn KOS_06ta -sn KOS_07ta -sn KOW_02ta -sn KOW_03ta -sn KOW_04ta -sn KOW_05ta -sn KOW_06ta -sn KOW_07ta -sn KOW_08ta -sn TKO_01ta -sn TKO_02ta -sn TKO_03ta -sn TKO_04ta -sn TKO_05ta -sn TKO_06ta -sn TKO_07ta -sn TKO_08ta -sn TRE_01ta -sn TRE_02ta -sn TRE_03ta -sn TRE_04ta -sn TRE_05ta -sn TRE_06ta -sn TRE_07ta -sn TRE_08ta -sn TRT_01ta -sn TRT_02ta -sn TRT_03ta -sn TRT_04ta -sn TRT_05ta -sn TRT_06ta -sn TRT_07ta -sn TRT_08ta -sn TRT_09ta -sn TZI_01ta -sn TZI_02ta -sn TZI_03ta -sn TZI_04ta -sn TZI_05ta -sn TZI_06ta -sn TZI_07ta -sn TZI_08ta -sn TZI_09ta -sn TZI_10ta -sn LAC_01ta -sn LAC_02ta -sn LAC_03ta -sn LAC_04ta -sn LAC_05ta -sn LAC_06ta -sn LAC_07ta -sn LAC_08ta -sn WEK_01ta -sn WEK_02ta -sn WEK_03ta -sn WEK_04ta -sn WEK_05ta -sn WEK_06ta -sn WEK_07ta -sn WEK_08ta -sn ZAP_01ta -sn ZAP_02ta -sn ZAP_03ta -sn ZAP_04ta -sn ZAP_05ta -sn ZAP_06ta -sn ZAP_07ta -sn ZAP_08ta

bcftools consensus -f AL8G14450_reference.fasta tetraploids_AL8G14450.vcf.gz -o tetraploids_AL8G14450.vcf.gz.fasta
# Applied 6 variants
```









**PyMOL代码**

```shell
color sand, (model diploids_g32048.t1 and resi 218:324) 
align cochlearia_diploids__g35052.t1,cochlearia_tetraploids_g35052.t1
color blue, (cochlearia_diploids__g35052.t1)
color marine, (cochlearia_tetraploids_g35052.t1)
select domain1, cochlearia_diploids__g35052.t1 and resi 42-131
show cartoon, domain1
color red, domain1
```

```shell
## PyMOL标注突变残基
select mutation_residue, diploids_g54384.t1 and resi 70+81+82+83+244+784+823+993+1029



color red, mutation_residue

show sticks, mutation_residue

select malectin_domain, diploids_g54384.t1 and resi 427-613
select Protein_kinase_domain, diploids_g54384.t1 and resi 694-960
```

```shell
color sand, (model diploids_g54384.t1 and resi 218:324)
select malectin_domain, diploids_g54384.t1 and resi 427-613

select Protein_kinase_domain, diploids_g54384.t1 and resi 694-960
show sticks, malectin_domain
```



```shell
color lime, (model diploids_g54384.t1 and resi 627-613)
color sand, (model diploids_g54384.t1 and resi 694-960)

color lime, (model tetraploid_g54384.t1 and resi 423-609)
color sand, (model tetraploid_g54384.t1 and resi 690-954)

color sand, (model arenosa_diploids_AL1G64410 and resi 307-551)
color sand, (model arenosa_tetraploids_AL1G64410 and resi 308-615)

select mutation_residue, tetraploid_g54384.t1 and resi 419+628+711
color red, mutation_residue
show sticks, mutation_residue
select mutation_residue2, diploids_g54384.t1 and resi 703
color red, mutation_residue2
show sticks, mutation_residue2
```

```shell
color violet, (model cochlearia_diploids__g35052.t1 and resi 43-131)
color pink, (model cochlearia_tetraploids_g35052.t1 and resi 42-130)
select mutation_residue, cochlearia_diploids_g35052.t1and resi 10+11
select mutation_residue2, cochlearia_tetraploids_g35052.t1 and resi 11


```

```shell
color limon, (model cochlearia_diploids_g2417.t1 and resi 106-339)
color limon, (model cochlearia_tetraploids_g2417.t1 and resi 103-335)
color darksalmon, (model arenosa_diploids_AL5G32850 and resi 82-291)
color darksalmon, (model arenosa_tetraploids_AL5G32850 and resi 82-291)

select mutation_residue, cochlearia_diploids_g2417.t1 and resi 12+30+28+46+152+155+156+368
select mutation_residue2, cochlearia_tetraploids_g2417.t1 and resi 152+155+156+260+358+359
select mutation_residue3, arenosa_diploids_AL5G32850 and resi 9+10
select mutation_residue4, arenosa_tetraploids_AL5G32850 and resi 10

```



```shell
color wheat, (model diploids_g10577.t1 and resi 252-268)
color sand, (model diploids_g10577.t1 and resi 299-377)
color lightblue, (model diploids_g10577.t1 and resi 425-483)
color lightpink, (model diploids_g10577.t1 and resi 485-661)
color purple, (model diploids_g10577.t1 and resi 863-1104)

```

```shell
color sand, (model diploids_g32048.t1 and resi 218-324)
color purple, (model diploids_g32048.t1 and resi 387-485)
```

























