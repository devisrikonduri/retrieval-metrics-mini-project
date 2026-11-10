# Retrieval Evaluation Results and Interpretation

## Comparison Table

| Query | Keyword rank | Semantic rank |
|---|---|---|
| my redis cache keeps showing old data | 8 | 1 |
| how do I add semantic search to a table I already have | miss | 2 |
| redis or memcached for caching | 1 | 2 |
| why did my query get slower after I added an index | miss | 1 |
| what does ACID actually guarantee | 2 | 1 |
| how do I keep my postgres online while changing the schema | 6 | 3 |
| my background jobs stop after every deploy | miss | 2 |
| how do I let my database accept more writes per second | 4 | 1 |
| sql or nosql for a new product | 1 | 3 |
| why does my redis memory keep climbing | miss | 2 |
| **Summary** | **MRR 0.30 · Recall@10 0.60** | **MRR 0.67 · Recall@10 1.00** |

## Interpretation

Overall, semantic search is clearly superior across both evaluation metrics, achieving an MRR of 0.67 compared to keyword search's 0.30 and a flawless Recall@10 of 1.00 versus 0.60. Keyword search only won on two specific queries—`redis or memcached for caching` and `sql or nosql for a new product`—both of which consist of exact, distinct technical terminology and proper nouns directly matching the document titles. In contrast, semantic search dominated the remaining queries (such as `my redis cache keeps showing old data` and `why did my query get slower after I added an index`), all of which describe operational symptoms, natural language questions, or paraphrased concepts where vocabulary mismatch causes keyword search to miss completely. A production engineering team would still keep the keyword search system around because it outperforms semantic search on exact keyword lookups and entity comparisons, making the two approaches natural complements for a hybrid search architecture.
