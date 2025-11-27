# Summary

This dataset (**ml-latest**) describes 5-star rating and free-text tagging activity from [MovieLens](http://movielens.org), a movie recommendation service. It contains **33,832,162 ratings** and **2,328,315 tag applications** across **86,537 movies**. These data were created by **330,975 users** between **January 09, 1995** and **July 20, 2023**. This dataset was generated on **July 20, 2023**.

Users were selected at random for inclusion. All selected users had rated at least one movie. No demographic information is included. Each user is represented by an ID, and no other information is provided.

The data are contained in the files:

* `genome-scores.csv`
* `genome-tags.csv`
* `links.csv`
* `movies.csv`
* `ratings.csv`
* `tags.csv`

More details about these files follow.

This is a *development* dataset and may change over time. It is **not appropriate for shared research results**. See available *benchmark* datasets for that purpose.

You can download this and other GroupLens datasets from: [http://grouplens.org/datasets/](http://grouplens.org/datasets/)

---

# Usage License

This dataset may be used for research purposes under these conditions:

* Do **not** imply endorsement by the University of Minnesota or GroupLens Research Group.
* Acknowledge use of the dataset in any resulting publications (see citation below).
* You may redistribute the dataset (including transformations) under the same license conditions.
* Commercial or revenue-generating uses require prior permission from a GroupLens faculty member.
* Executable scripts are provided "as is" without any warranty. You assume all risks associated with their use.

The University of Minnesota, its affiliates, or employees are **not liable** for damages arising from the use or inability to use these programs.

For questions or comments, email: `grouplens-info@umn.edu`

---

# Citation

To acknowledge use of the dataset in publications, cite:

> F. Maxwell Harper and Joseph A. Konstan. 2015.
> *The MovieLens Datasets: History and Context.*
> ACM Transactions on Interactive Intelligent Systems (TiiS) 5, 4: 19:1–19:19.
> [https://doi.org/10.1145/2827872](https://doi.org/10.1145/2827872)

---

# Further Information About GroupLens

GroupLens is a research group in the Department of Computer Science and Engineering at the University of Minnesota. Since 1992, their work has explored:

* Recommender systems
* Online communities
* Mobile and ubiquitous technologies
* Digital libraries
* Local geographic information systems

MovieLens is a recommender system operated by GroupLens. Try it at [http://movielens.org](http://movielens.org)

Interested in collaborating? Contact: `grouplens-info@cs.umn.edu`

---

# Content and Use of Files

## Formatting and Encoding

* All files are in **CSV** format with a single header row.
* Columns with commas are escaped with double-quotes (`"`).
* Files are **UTF-8** encoded.
* Ensure your software supports UTF-8 to view accented characters correctly (e.g., *Misérables*).

---

## User IDs

* Users were randomly selected and anonymized.
* IDs are consistent across `ratings.csv` and `tags.csv`.

---

## Movie IDs

* Only movies with at least one rating or tag are included.
* Movie IDs are consistent across:

  * `ratings.csv`
  * `tags.csv`
  * `movies.csv`
  * `links.csv`

Movie ID `1` corresponds to [https://movielens.org/movies/1](https://movielens.org/movies/1)

---

## `ratings.csv`

Format:

```
userId,movieId,rating,timestamp
```

* Ordered by `userId`, then `movieId`
* Ratings use a **0.5 to 5.0** star scale
* Timestamps = seconds since **Jan 1, 1970 (UTC)**

---

## `tags.csv`

Format:

```
userId,movieId,tag,timestamp
```

* Ordered by `userId`, then `movieId`
* Tags = user-generated short descriptions
* Timestamps = seconds since **Jan 1, 1970 (UTC)**

---

## `movies.csv`

Format:

```
movieId,title,genres
```

* Titles include the year of release in parentheses
* Genres are **pipe-separated** values from this list:

```
Action, Adventure, Animation, Children's, Comedy, Crime, Documentary,
Drama, Fantasy, Film-Noir, Horror, Musical, Mystery, Romance,
Sci-Fi, Thriller, War, Western, (no genres listed)
```

---

## `links.csv`

Format:

```
movieId,imdbId,tmdbId
```

* `movieId` → [MovieLens](https://movielens.org/movies/1)
* `imdbId` → [IMDb](https://www.imdb.com/title/tt0114709/)
* `tmdbId` → [TMDb](https://www.themoviedb.org/movie/862)

Note: Use of external sources is subject to their terms.

---

## Tag Genome (`genome-scores.csv` and `genome-tags.csv`)

The **Tag Genome** is a data structure representing tag relevance scores for movies. It's a dense matrix encoding how strongly each movie exhibits certain properties (e.g., *thought-provoking*, *realistic*).

It is based on user-contributed content (tags, ratings, reviews) and computed with machine learning.

### `genome-scores.csv` format:

```
movieId,tagId,relevance
```

### `genome-tags.csv` format:

```
tagId,tag
```

Note: `tagId` values may differ between dataset versions.

Cite the following if using Tag Genome data:

> Jesse Vig, Shilad Sen, and John Riedl. 2012.
> *The Tag Genome: Encoding Community Knowledge to Support Novel Interaction.*
> ACM TiiS 2, 3: 13:1–13:44.
> [https://doi.org/10.1145/2362394.2362395](https://doi.org/10.1145/2362394.2362395)

---

## Cross-Validation

Previous MovieLens versions included cross-folds or scripts. These are no longer bundled. For modern tools and approaches, see:

* [LensKit](http://lenskit.org)
