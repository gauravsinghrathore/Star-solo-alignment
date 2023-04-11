# Star-solo-alignment using CellRanger .bam files

Sometimes Velocyto CLI does not detect key Genes while creating count matrix.
Star Solo tends to solve the problem 

The new count metrix can be created using the bam files as output from cellranger


STAR --soloType CB_UMI_Simple --genomeDir /nfsdata/data/ref/velocity/star_latest --readFilesIn /path/to/bam/file/possorted_genome_bam.bam --readFilesType SAM SE --readFilesCommand samtools view -F 0x100 --soloInputSAMattrBarcodeSeq CR UR --outFilterScoreMin 30 --soloCBmatchWLtype 1MM_multi_Nbase_pseudocounts --soloUMIfiltering MultiGeneUMI_CR --soloUMIdedup 1MM_CR --soloCBlen 16 --soloUMIlen 12 --soloCBwhitelist /nfsdata/data/ref/velocity/3M-february-2018.txt --soloFeatures Gene Velocyto --runThreadN 50
