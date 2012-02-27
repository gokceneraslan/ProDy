.. _prody-align:

*******************************************************************************
prody align
*******************************************************************************

Align models in a PDB file or multiple structures in separate PDB files.

Usage
===============================================================================

Running :command:`prody align -h` displays::

  usage: prody align [-h] [--quiet] [--examples] [-p STR] [-s SELSTR] [-m INT]
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

Examples
===============================================================================

Running :command:`prody align --examples` displays::

  Align models in PDB structure or multiple PDB structures and save
  aligned coordinate sets.  When multiple structures are aligned, ProDy
  will match  chains and use best match for aligning the structures.
  Note that options are not used when aligning multiple structures.
  
  Fetch PDB structure 2k39 and align models:
  
      $ prody align 2k39
  
  Fetch PDB structure 2k39 and align models using backbone of residues
  with number smaller than 71:
  
      $ prody align 2k39 --select "backbone and resnum < 71"
  
  Fetch PDB structures 1p38, 1r39 and 1zz2 and superpose 1r39 and 1zz2
  onto 1p38:
  
      $ prody align 1p38 1r39 1zz2