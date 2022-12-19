# Genomics
Filtering SNPs from a VCF file

#To create a vcf file which contains only PASS bi-allelic coding SNPs with VQSLOD > 6

bcftools view \
--include 'FILTER="PASS" && N_ALT=1 && CDS==1 && TYPE="snp" && VQSLOD>6.0' \
--output-type z \
--output-file output/output2_filename.vcf.gz \
/home/aaobeng1/vcf/Pf_60_public_Pf3D7_v3.final.vcf.gz

bcftools index --tbi vcf/output_filename.vcf.gz
