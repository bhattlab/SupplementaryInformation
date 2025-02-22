# SmORFinder Supplementary Information

This includes the full train, dev, and test sets that were used in the original *SmORFinder* paper.

Please download and decompress the table with:

	wget https://github.com/bhattlab/SupplementaryInformation/raw/master/SmORFinder/datasets.tar.gz
	tar -zxvf datasets.tar.gz

The file dataset_FINAL.tsv is a tab-delimited file that includes all examples split into a train, dev, and a test set.

The columns include in this file include:

set - either train, dev, or test.
smorfam - The smORF family or cluster that the example belongs to.
name - The unique name of the example.
origin - If the sequence was real (from a real microbial genome) or fake (generated by tetramer shuffling of real sequences).
y - Either "positive" (true smORF) or "negative" (false smORF).
upstream - The 5-prime or upstream DNA sequence.
downstream - The 3-prime or downstream DNA sequence.
smorf - The DNA sequence of the smORF

The file dataset_HOLDOUT.tsv includes the same columns as dataset_FINAL.tsv. It differs in that the train and dev sets were combined together and shuffled to create two distinct dev sets, a dev_seen and a dev_unseen set. The dev_seen set includes smORF family examples where other members of the family were represented in the train set. The dev_unseen set are a set of smORF families that were intentionally excluded from the train set. This set can be used to determine how well you model generalizes to unseen examples.
