.. _prody-align:

*******************************************************************************
prody align
*******************************************************************************

Align models in a PDB file or multiple structures in separate PDB files.

Usage
===============================================================================

Running :command:`prody align -h` displays::

  usage: prody align [-h] [--quiet] [--examples] [-p STR] [-s SELSTR] [-m INT]
                     [-i INT] [-o INT]
                     pdb [pdb ...]
  
  positional arguments:
    pdb                   PDB identifier(s) or filename(s)
  
  optional arguments:
    -h, --help            show this help message and exit
    --quiet               suppress info messages to stderr
    --examples            show usage examples and exit
    -p STR, --prefix STR  prefix for output files, default is PDB_aligned
    -s SELSTR, --select SELSTR
                          selection string (default: "calpha")
    -m INT, --model INT   for NMR files, reference model index (default: 1)
    -i INT, --seqid INT   percent sequence identity (default: 90)
    -o INT, --overlap INT
                          percent sequence overlap (default: 90)

Examples
===============================================================================

Running :command:`prody align --examples` displays::

  Align models in PDB structure or multiple PDB structures and save
  aligned coordinate sets.  When multiple structures are aligned, ProDy
  will match chains based on sequence alignment and use best match for
  aligning the structures.
  
  Fetch PDB structure 2k39 and align models (reference model is the
  first model):
  
      $ prody align 2k39
  
  Fetch PDB structure 2k39 and align models using backbone of residues
  with number less than 71:
  
      $ prody align 2k39 --select "backbone and resnum < 71"
  
  Align 1r39 and 1zz2 onto 1p38 using residues with number less than
  300:
  
      $ prody align --select "resnum < 300" 1p38 1r39 1zz2
  
  Align all models of 2k39 onto 1aar using residues 1 to 70 (inclusive):
  
      $ prody align --select "resnum 1 to 70" 1aar 2k39
  
