# Panagram: Interactive, alignment-free pan-genome browser  

#### Katie Jenike, Sam Kovaka, Shujun Ou, Stephen Hwang, Srividya Ramakrishnan, Ben Langmead, Zach Lippman, Michael Schatz


An alignment-free pan-genome viewer

# Installation

```
> pip install git+https://github.com/kjenike/panagram.git --user
```
OR
```
> git clone --recursive https://github.com/kjenike/panagram.git
> cd panagram
> pip install .
```

# Preprocessing
Usage:
```
usage: panagram index [-h] [-k int] <genomes_in>.tsv -o <out_dir>/

  Anchor KMC bitvectors to reference FASTA files to create pan-kmer bitmap

  genomes_in str        TSV file with each genome ID in the first column and the path to a
                        gzipped fasta in the second column
  -k int, --k int       K-mer (default: 21)
  -o str, --out_dir str
                        Output directory for panagram index (default: None)

```

Where `<genome_fastas.tsv>` is a tab-separated file with the first column being a genome ID containing only alphanumeric characters, and the second a path to a gzipped fasta file. Will output all files to directory named `<index_dir>/`.

This is a work in progress, and does not yet produce the full configuration file required to run `panagram view`. It does, however, perform the most computationaly intensive steps required for indexing the pan-genome.

# View

Usage:
```
usage: panagram view [-h] <config>.txt
  Display panagram viewer
```

Runs a local Dash server. Browser can be viewed at http://127.0.0.1:8050/ by default.

# Bitdump

Usage:
```
usage: panagram bitdump [-h] [-v bool] index_dir coords step
  Query pan-kmer bitmap generated by "panagram index"/

  index_dir             Panagram index directory
  coords                Coordinates to query in chr:start-end format
  step                  Spacing between output kmers (optimized for multiples
                        of 100) (default: 1)
  -v bool, --verbose bool
                        Output the full bitmap (default: False)
```


## More information coming soon!
