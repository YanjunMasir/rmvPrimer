rmvPFBAM
===========================
Used to remove primers from BAM files.

```
PROGRAM: rmvPFBAM
VERSION: 1.0.0
PLATFORM: Linux
AUTHOR: YanjunMa
EMAIL:mayanjun0010@yeah.net
DATE: 2021-02-05
```


## Description
* This tool is used to remove primer from BAM.
* The input of the tool is BAM and amplicon file. The format of the amplicon file can be referenced in the example folder.


## Requirement
* Linux
* Python 3.0
* The needed module is :pysam、multiprocessing、regex.


## Usage
```
Options：
-a  Amplicon file. File format is: amplicon tag, front primer sequence, reverse primer sequence, gene, chrom, start position of the front primer
                end position of the front primer, start position of the reverse primer, end position of the reverse primer
                Ex: RB1_11_14_RB1_1,GCAGCAGCTGGGTCATCTAT,TGAAACACTATAAAGCCATGAATAACA,RB1,chr13,48942506,48942526,48942776,48942803
                    RB1_7_14_RB1_1,TCTACCCTGCGATTTTCTCTCA,TCCTGTCAGCCTTAGAACCA,RB1,chr13,48934079,48934101,48934338,48934358
 -b  The input BAM file that need to remove the primer.
 -l  Length of the read.
 -t  Temp folder.
 -o  The output BAM file. You can also specify the folder of the BAM file. Ex: project/output/SRR866441.rmp.bam
 -e  The error count you can tolerant when comparing the primer with the read sequence.
```

## Example
```
rmvPFBAM -a amplicon.txt -b SRR866441.bam -l 150 -t temp -o output/SRR866441.rmp.bam -e 2
```
