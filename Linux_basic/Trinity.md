# Trinity
More detail about trinity here: https://github.com/trinityrnaseq/trinityrnaseq/wiki/Running-Trinity

Before I start Trinity run, I will like to combine all the R1_paired together and all the R2_paired together by doing:
```
cat *_R1_paired.fastq.gz > XT_R1.fastq.gz
cat *_R2_paired.fastq.gz > XT_R2.fastq.gz
```

## How to run trinity
```bash
time /home/xue/software//home/xue/software/trinityrnaseq-Trinity-v2.5.1/Trinity --seqType fq  --left /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R1.fastq.gz --right /home/xue/tropicalis_gonad_transcriptome_Dec2018/trim/XT_R2.fastq.gz --CPU 20 --inchworm_cpu 6 --full_cleanup --max_memory 200G --min_kmer_cov 2 --output /home/xue/tropicalis_gonad_transcriptome_Dec2018/tropicali_gonad_transcriptome_trinityOut
```
Below is the explaination of what we included in the above command:
- --seqType <string>      :type of reads: ('fa' or 'fq')
- --left  <string>    :left reads, one or more file names (separated by commas, no spaces)
- --right <string>    :right reads, one or more file names (separated by commas, no spaces)
- --CPU <int>                     :number of CPUs to use, default: 2
- --inchworm_cpu <int>           :number of CPUs to use for Inchworm, default is min(6, --CPU option); capped at 6, perform wouldn't increase even increase higher than 6
-  --full_cleanup                  :only retain the Trinity fasta file, rename as ${output_dir}.Trinity.fasta
- --max_memory <string>      :suggested max memory to use by Trinity where limiting can be enabled. (jellyfish, sorting, etc) provided in Gb of RAM, ie.  '--max_memory 10G'
- --min_kmer_cov <int>           :min count for K-mers to be assembled by Inchworm (default: 1)
- --output <string>               :name of directory for output (will be created if it doesn't already exist)

How to see the full usage
```
/home/xue/software/trinityrnaseq-Trinity-v2.4.0/Trinity --show_full_usage_info
```
