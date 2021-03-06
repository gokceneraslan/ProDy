.. _prody-anm:

*******************************************************************************
prody anm
*******************************************************************************

Perform ANM calculations and output the results in plain text, NMD, and 
graphical formats.

Usage
===============================================================================

Running :command:`prody anm -h` displays::

  usage: prody anm [-h] [--quiet] [--examples] [-n INT] [-s SELSTR] [-c FLOAT]
                   [-g FLOAT] [-m INT] [-a] [-o PATH] [-e] [-r] [-q] [-v] [-z]
                   [-b] [-l] [-k] [-p STR] [-f STR] [-d STR] [-x STR] [-A] [-R]
                   [-Q] [-B] [-K] [-F STR] [-D INT] [-W FLOAT] [-H FLOAT]
                   pdb
  
  positional arguments:
    pdb                   PDB identifier or filename
  
  optional arguments:
    -h, --help            show this help message and exit
    --quiet               suppress info messages to stderr
    --examples            show usage examples and exit
  
  parameters:
    -n INT, --number-of-modes INT
                          number of non-zero eigenvalues/vectors to calculate
                          (default: 10)
    -s SELSTR, --select SELSTR
                          atom selection (default: "protein and name CA or
                          nucleic and name P C4' C2")
    -c FLOAT, --cutoff FLOAT
                          cutoff distance (A) (default: 15.0)
    -g FLOAT, --gamma FLOAT
                          spring constant (default: 1.0)
    -m INT, --model INT   model that will be used in the calculations
  
  output:
    -a, --all-output      write all outputs
    -o PATH, --output-dir PATH
                          output directory (default: ".")
    -e, --eigenvs         write eigenvectors/values
    -r, --cross-correlations
                          write cross-correlations
    -q, --square-fluctuations
                          write square-fluctuations
    -v, --covariance      write covariance matrix
    -z, --npz             write compressed ProDy data file
    -b, --beta-factors    write B-factors
    -l, --hessian         write Hessian matrix
    -k, --kirchhoff       write Kirchhoff matrix
  
  output options:
    -p STR, --file-prefix STR
                          prefix for output files (default: pdb_anm)
    -f STR, --number-format STR
                          delimiter (default: "%12g")
    -d STR, --delimiter STR
                          delimiter (default: " ")
    -x STR, --extension STR
                          file extension (default: .txt)
  
  figures:
    -A, --all-figures     save all figures
    -R, --cross-correlations-figure
                          save cross-correlations
    -Q, --square-fluctuations-figure
                          save square-fluctuations
    -B, --beta-factors-figure
                          save beta-factors
    -K, --contact-map     save contact map (Kirchhoff matrix)
  
  figure options:
    -F STR, --figure-format STR
                          figure format, one of eps, pdf, png, ps, raw, rgba,
                          svg, svgz (default: pdf)
    -D INT, --resolution INT
                          figure resolution (dpi) (default: 300)
    -W FLOAT, --width FLOAT
                          figure width (inch) (default: 8.0)
    -H FLOAT, --height FLOAT
                          figure height (inch) (default: 6.0)

Examples
===============================================================================

Running :command:`prody anm --examples` displays::

  This command performs ANM calculations for given PDB structure and
  outputs results in NMD format. If an identifier is passed, structure
  file will be downloaded from the PDB FTP server.
  
  Fetch PDB 1p38, run ANM calculations using default parameters, and
  write NMD file:
  
    $ prody anm 1p38
  
  Fetch PDB 1aar, run ANM calculations using default parameters for
  chain A carbon alpha atoms with residue numbers less than 70, and save
  all of the graphical output files:
  
    $ prody anm 1aar -s "calpha and chain A and resnum < 70" -A
