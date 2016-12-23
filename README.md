# enrichr_cli
Python script to use enrichr from command line (http://amp.pharm.mssm.edu/Enrichr/)

Python script to query enrichr from command line.

Required python libraries:
  -json, requests, sys, os

Input is a newline-separated list of gene symbols, either from a file or on stdin.

Usage:
  -python enrichR.py genelist.txt                                        [using default databases, see further]
  -python enrichR.py genelist GO_Molecular_Function_2015                 [using just one database]
  -python enrichR.py genelist GO_Molecular_Function_2015 Reactome_2016   [using just two databases]
  -cat genelist.txt | python enrichR.py -                                [reading from a pipe]

Output:
  -Per used database a file will be created containing the enrichment results.

To get a list of all available databases:
  python enrichR.py databases
Default databases, used without specifying a database:
  -KEGG_2015
  -BioCarta_2016
  -WikiPathways_2016
  -Reactome_2016
  -GO_Biological_Process_2015
  -GO_Cellular_Component_2015
  -GO_Molecular_Function_2015
  -MSigDB_Computational
  -Panther_2016
Note: these databases are hardcoded in the script and as such will not follow updates from Enrichr automatically.
  
If you specify a database which is not available you will receive a warning. 
If not a single valid database is specified the default set will be used.



I'm not affiliated to the authors of Enrichr but just use their API.
