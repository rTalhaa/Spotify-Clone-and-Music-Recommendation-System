# Music Recommender System

## Overview
This project focuses on building and evaluating a collaborative-filter based recommender system using a music dataset.

## Dataset
The project utilizes the [Million Song Dataset](http://millionsongdataset.com/) (MSD), compiled by Thierry Bertin-Mahieux, Daniel P.W. Ellis, Brian Whitman, and Paul Lamere. Detailed in their publication at the 12th International Society for Music Information Retrieval Conference (ISMIR 2011).

The MSD contains metadata (artist, album, year, etc.), tags, partial lyrics, and derived acoustic features for one million songs. User interaction data is sourced from the [Million Song Dataset Challenge](https://www.kaggle.com/c/msdchallenge), presented by McFee, B., Bertin-Mahieux, T., Ellis, D. P., & Lanckriet, G. R. at the 21st International Conference on World Wide Web.

This interaction data consists of implicit feedback: play count data for about one million users. The data is pre-partitioned into training, validation, and test sets:
  - `cf_train.parquet`
  - `cf_validation.parquet`
  - `cf_test.parquet`

Each file contains tuples of `(user_id, count, track_id)`, indicating the play count for specific tracks by users. For example:

|    | user_id                                  |   count | track_id           |
|---:|:-----------------------------------------|--------:|:-------------------|
|  0 | b80344d063b5ccb3212f76538f3d9e43d87dca9e |       1 | TRIQAUQ128F42435AD |
|  1 | b80344d063b5ccb3212f76538f3d9e43d87dca9e |       1 | TRIRLYL128F42539D1 |
|  2 | b80344d063b5ccb3212f76538f3d9e43d87dca9e |       2 | TRMHBXZ128F4238406 |
|  3 | b80344d063b5ccb3212f76538f3d9e43d87dca9e |       1 | TRYQMNI128F147C1C7 |
|  4 | b80344d063b5ccb3212f76538f3d9e43d87dca9e |       1 | TRAHZNE128F9341B86 |

## Collaborative-filter Based Recommender System
The recommender system employs [Spark's alternating least squares (ALS) method](https://spark.apache.org/docs/2.4.7/ml-collaborative-filtering.html) to learn latent factor representations for users and items.

Key hyper-parameters tuned for optimal performance on the validation set include:
  - *Rank*: Dimension of the latent factors.
  - Regularization parameter.

### Evaluation
Model accuracy was assessed on validation and test data by predicting the top 500 items for each user. The primary metric used was mean Average Precision (mAP) (refer to PySpark's [ranking metrics](https://spark.apache.org/docs/2.4.7/mllib-evaluation-metrics.html#ranking-systems) for more details).

### Infrastructure
Model training was performed on [The Peel Big Data cluster](https://sites.google.com/a/nyu.edu/nyu-hpc/documentation/peel) at NYU High Performance Computing. The cluster features 18 data nodes running Cloudera CDH version 6.3.4, including Hadoop 3.0.0 and Spark 2.4.0.

## Popularity-based Model as Baseline
Additionally, a popularity-based model was implemented as a baseline for comparison against the collaborative-filter based model. For more details, see this [Springer link](https://link.springer.com/chapter/10.1007/978-1-4899-7637-6_3), section 3.2, or the `bias` implementation provided by [lenskit](https://lkpy.readthedocs.io/en/stable/bias.html).

## Results
For a detailed report, Please request and will be provided.

