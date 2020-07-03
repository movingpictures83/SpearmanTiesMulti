# SpearmanTiesMulti
# Language: Python
# Input: TXT (rank files)
# Output: CSV (correlations)
# Tested with: PluMA 1.1, Python 3.6
# Dependency: scipy==1.4.1

PluMA plugin to compute Spearman correlations (Spearman, 1904) given
 a single set of samples and multiple sets of entities and ranks.
This can be useful in multi-omics data for example where different -omics
data may use separate metrics, making it necessary to compute separate sets of ranks.

The input TXT file contains a list of rank files, each on its own separate line, i.e.:

rank1.csv
rank2.csv

These CSV files are assumed to be formatted such that samples are represented by rows
and entities by columns, with entry (i, j) storing the abundance of entity j in sample i.
Note that sample names must match in all CSV files.

A single output set of Spearman correlations is then computed for the union of all 
entities from the CSV files.

This plugin's functionality is identical to another plugin SpearmanMulti, except that this
also contains the built-in functionality for handling rank ties that is in SpearmanTies.
