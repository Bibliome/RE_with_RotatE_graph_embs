# Relation Extraction with RotatE Graph Embeddings

Injection of knowledge graph embedding (RotatE) into BERT for biomedical Relation Extraction (RE).

### ${\color{orange}Use \ our \ methods \ on \ other \ corpora}$

- Refer to the README file in the folder "preprocessing" to prepare your data.
- Put all datafiles under /data/${corpus_name}.
- Set the following values in the slurm files (both run_no_kb and run_with_kb): number of labels (nl); number of training epochs (ne); corpus name (corpus); learning rate (lr). Check all available options by:
  ```
  python3 main.py --help
  ```
- Set --force_cpu if no GPU is available
- Add class weights to "class_weights" in utils.py. For each of K classes $c_i$, its weight should be $\frac{\sum_jN_j}{N_i}$, where $N_i$ is the number of training examples for $c_i$.

#### :raised_hand: In case you want to change BERT model (PubMedBERT by default)

- add the corresponding config.json in the folder of "config"
- add its Huggingface model card name to "model_download_shortcuts" in utils.py

