# heterozygosity

Calculating heterozygosity on computecanada with bam files

```bash
#!/bin/sh
#SBATCH --job-name=bwa_505
#SBATCH --nodes=1
#SBATCH --ntasks-per-node=1
#SBATCH --time=48:00:00
#SBATCH --mem=128gb
#SBATCH --output=het.%J.out
#SBATCH --error=het.%J.err
#SBATCH --account=def-ben

#SBATCH --mail-user=premacht@mcmaster.ca
#SBATCH --mail-type=BEGIN
#SBATCH --mail-type=END
#SBATCH --mail-type=FAIL
#SBATCH --mail-type=REQUEUE
#SBATCH --mail-type=ALL

for i in *.bam;do angsd -i ${i} -anc /scratch/premacht/new_project_Apr_2023/new_data_Jun23/reference_genome/XENTR_10.0_genome_scafconcat_goodnamez.fasta -dosaf 1 -GL 1  -out ${i}out ; done
```
