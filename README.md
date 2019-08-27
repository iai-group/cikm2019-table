# Auto-completion for Data Cells in Relational Tables

This repository contains resources developed within the following paper:

> S. Zhang and K. Balog. Auto-completion for Data Cells in Relational Tables. In: *Proceedings of The 28th ACM International Conference on Information and Knowledge Management (CIKM ’19)*, Nov 2019.


## Test collection

The table corpus is [WikiTables](http://websail-fe.cs.northwestern.edu/TabEL/), which comprises 1.6M tables extracted from Wikipedia. We proproceeed it and make it public downloadable [here](http://iai.group/downloads/smart_table/WP_tables.zip).

The `data/queries.txt` file contains the search queries. 

The `data/qrels.txt` file contains the relevance assessments (in TREC qrels format).  

## Data

We utilize word2vec trained on Google news, and you can find it [here](https://github.com/mmihaltz/word2vec-GoogleNews-vectors). You can find the graph embeddings [here](http://data.dws.informatik.uni-mannheim.de/rdf2vec/).



## Methods and results

The `runfile/` folder contains the table rankings generated by the various methods (in TREC runfile format) (cf. Table 5 in the paper).


|Source|Method|Runfile|Sources| used| Empty| excluded|Empty|included|
| -- | -- | -- | -- | -- | -- | -- | --|-- |
|| ||KB|TC| NDCG@5|	NDCG@10|	NDCG@5|	NDCG@10|
|Single-source| KBLookupED || T | | 0.2635 | 0.2652 | 0.2780 | 0.2806 |
|| InfoGather, top, UNI  || | T | 0.4563  | 0.4710 | 0.4158 | 0.4302|
|| InfoGather, top, L2V  || | T | 0.4868  | 0.4978 | 0.4413 | 0.4537 |
||  TMatch, top, UNI  ||| T | 0.4744  | 0.4873 | 0.4297| 0.4417|
|| TMatch, top, L2V  ||| T | 0.5046  | 0.5139 | 0.4531 | 0.4624 |
|Multi-source|  OTG ||  T | T | 0.5856 | 0.6062 | 0.5185 | 0.5367 |
|| CellAutoComplete (feat. I)  || T | T | 0.6641|  0.6826|   0.5766| 0.5954|
|| CellAutoComplete (feat. I+II)  || T | T | 0.6844| 0.7034| 0.5905| 0.6100|
||CellAutoComplete (feat. I+II+III)  || T | T | 0.7570| 0.7641| 0.6716| 0.6785|



The evaluation scores are reported using [trec_eval](https://github.com/usnistgov/trec_eval).


## Citation
```
@inproceedings{Zhang:2019:ADC,
    author = {Zhang, Shuo and Balog, Krisztian},
    title = {Auto-completion for Data Cells in Relational Tables},
    booktitle = {Proceedings of the 28th ACM International Conference on Information and Knowledge Management (CIKM ’19)},
    year = {2019},
    pages = {},
}
```

## Contact
If you have any questions, please contact Shuo Zhang at shuo.zhang@uis.no.
