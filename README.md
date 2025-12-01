# hic-analysis

This page explains how to run the hic analysis for the high quality reference genomes.

**Step 1.** Run the 01_download.sh script, pass in the RUNID and RUNDIR as arguments. 

**example**
```
bash 01_download.sh "NEXT_251118_AD" "/scratch/pawsey0964/lhuet/hic-analysis"
```
**Step 2.** Stage the assembly files, create a list of OG numbers you are running the complexity anlysis for and call it OG-list.sh. Then run the 02_get_primary_assemblies.sh script. Pass in the download path. 

**example**
```
bash 02_get_primary_assemblies.sh "/scratch/pawsey0964/lhuet/hic-analysis"
```
**Step 3.** Put the assemblies into the hic directories, the 03_run_hiline.sh and 04_loop.sh into the run directory 
```
**example**

/scratch/pawsey0964/lhuet/hic-analysis/NEXT_250325_AD/OG37H-1_HICL> rclone tree .
/
├── OG37H-1_HICL_S1_L001_R1_001.fastq.gz
├── OG37H-1_HICL_S1_L001_R2_001.fastq.gz
├── OG37H-1_HICL_ds.5a7614fa2c6543b39686cf1f2131fe34.json
├── OG37_v240116.hifi1.0.hifiasm.p_ctg.fasta

# where the run directory would be
/scratch/pawsey0964/lhuet/hic-analysis/NEXT_250325_AD/
```
**Step 4.** Update the loop script for your samples and submit the script
```
**example** 
bash 04_loop.sh
```
