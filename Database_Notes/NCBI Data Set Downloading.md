NCBI Data Downloading

Install NCBI Dataset Downloader
## *Linux*

curl -O https://ftp.ncbi.nlm.nih.gov/pub/datasets/command-line/v2/linux-amd64/datasets
chmod +x datasets

### Download by assembly accession

If `"GCA_000150715.1"` still exists in the database (GenBank), run:

`./datasets download genome accession GCA_000150715.1 --filename asm15071v1.zip`

Then unzip:

`unzip asm15071v1.zip -d asm15071v1`

Inside `asm15071v1/ncbi_dataset/data/GCA_000150715.1/` you’ll find the genomic FASTA:

`*_genomic.fna`

This exact command pulls the correct FASTA for that assembly _if_ it still has records in NCBI’s Datasets.


##  Alternative: search by taxon name (Option B)

If the accession is deprecated and you don’t know the organism name:

`./datasets download genome taxon "organism name" --filename myorg.zip`

Replace `"organism name"` with the species or strain name. That will fetch the latest assembly package.

---
## What MAKER2 actually expects

In `maker_opts.ctl`:

`est=transcripts.fasta protein=proteins.fasta`

Even though the parameter is called `est=`, **you put transcript FASTA there**.

This is normal and explicitly supported by MAKER2.
