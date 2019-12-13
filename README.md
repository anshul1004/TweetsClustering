# TweetsClustering

Twitter provides a service for posting short messages. In practice, many of the tweets are very
similar to each other and can be clustered together. By clustering similar tweets together, we can
generate a more concise and organized representation of the raw tweets, which will be very
useful for many Twitter-based applications (e.g., truth discovery, trend analysis, search ranking,
etc.)

Here, the tweets are clustered using Jaccard distance metric and K-means clustering algorithm.

# Jaccard Distance

The Jaccard distance, which measures dissimilarity between two sample sets (A and B). It is
defined as the difference of the sizes of the union and the intersection of two sets divided by the
size of the union of the sets. <br />
Dist(A, B) = 1 - |A intersection B|/|A union B|

For example, consider the following tweets: <br />
Tweet A: the long march <br />
Tweet B: ides of march <br />
|A intersection B | = 1 and |A union B | = 5, therefore the distance is 1 – (1/5)

Jaccard Distance Dist(A, B) between tweet A and B has the following properties:
1. It is small if tweet A and B are similar.
2. It is large if they are not similar.
3. It is 0 if they are the same.
4. It is 1 if they are completely different (i.e., no overlapping words).

# Dataset Used

https://archive.ics.uci.edu/ml/datasets/Health+News+in+Twitter

# Tweets Preprocessing

Firstly, the tweets are preprocessed using the following steps:
- tweet ids and timestamps are removed
- words that starts with the symbol '@', e.g., @AnnaMedaris, are removed
- hashtag symbols are removed, e.g., #depression is converted to depression
- any URL are removed
- every word is converted to lowercase

# K-Means Clustering Algorithm

K-means clustering algorithm is implemented from scratch, without using any machine learning libraries

Output results on one of the datasets is provided in "Report.pdf".

# Steps To Run

1) If the system don't have python Installed in it, first install python (version greater than or equal v3.7)
	- https://www.python.org/downloads/
2) The code uses the following python native libraries
        - random
	- re
	- math
3) In the root directory of the project, execute the given command from command line:
	- "python main.py"

4) Output from a sample run is also stored in a file named "output.txt" for the reference.

Notes :
 a) The code uses "bbchealth.txt" by default for the tweets data.
	- A user can change the url path to another data file as desired from the given files.

 b) The code uses, "3 clusters" by default and performs "5 experiments" one after another.
	- Each experiment increases the number of clusters being used from the previous experiment by 1.
	- A user can change the default value of intial clusters (k) and number of experiments to be performed.

 c) The program returns the value of SSE (sum of squared error) and size of each cluster after every experiment.

 d) A user can also print tweets in each cluster by uncommenting certain part of code written in the __main__.
