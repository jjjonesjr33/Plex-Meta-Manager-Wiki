You can find items using the features of [IMDb.com](https://www.imdb.com/) (IMDb).

| Name                      | Attribute    | Description                                                                                                                                               | Works with Movies  |  Works with Shows  | Works with Playlists and Custom Sort |
|:--------------------------|:-------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------|:------------------:|:------------------:|:------------------------------------:|
| [IMDb ID](#imdb-id)       | `imdb_id`    | Gets the movie/show specified.                                                                                                                            | :heavy_check_mark: | :heavy_check_mark: |                 :x:                  |
| [IMDb Chart](#imdb-chart) | `imdb_chart` | Gets every movie/show in an IMDb Chart like [IMDb Top 250 Movies](https://www.imdb.com/chart/top).                                                        | :heavy_check_mark: | :heavy_check_mark: |          :heavy_check_mark:          |
| [IMDb List](#imdb-list)   | `imdb_list`  | Gets every movie/show in an IMDb List, [IMDb Keyword Search](https://www.imdb.com/search/keyword/), or [IMDb Search](https://www.imdb.com/search/title/). | :heavy_check_mark: | :heavy_check_mark: |          :heavy_check_mark:          |

## IMDb ID
Gets the movie/show specified.

The expected input is an IMDb ID. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Star Wars (Animated Shows):
    imdb_id: tt0458290, tt2930604
```

## IMDb Chart
Finds every item in an IMDb Chart.

The expected input are the options below. Multiple values are supported as either a list or a comma-separated string.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

| Name                                                                           | Attribute        | Works with Movies  |  Works with Shows  |
|:-------------------------------------------------------------------------------|:-----------------|:------------------:|:------------------:|
| [Box Office](https://www.imdb.com/chart/boxoffice)                             | `box_office`     | :heavy_check_mark: |        :x:         |
| [Most Popular Movies](https://www.imdb.com/chart/moviemeter)                   | `popular_movies` | :heavy_check_mark: |        :x:         |
| [Top 250 Movies](https://www.imdb.com/chart/top)                               | `top_movies`     | :heavy_check_mark: |        :x:         |
| [Top Rated English Movies](https://www.imdb.com/chart/top-english-movies)      | `top_english`    | :heavy_check_mark: |        :x:         |
| [Most Popular TV Shows](https://www.imdb.com/chart/tvmeter)                    | `popular_shows`  |        :x:         | :heavy_check_mark: |
| [Top 250 TV Shows](https://www.imdb.com/chart/toptv)                           | `top_shows`      |        :x:         | :heavy_check_mark: |
| [Top Rated Indian Movies](https://www.imdb.com/india/top-rated-indian-movies/) | `top_indian`     | :heavy_check_mark: |        :x:         |
| [Lowest Rated Movies](https://www.imdb.com/chart/bottom)                       | `lowest_rated`   | :heavy_check_mark: |        :x:         |

```yaml
collections:
  IMDb Top 250:
    imdb_chart: top_movies
    collection_order: custom
    sync_mode: sync
```

## IMDb List
Finds every item in an IMDb List, [IMDb Keyword Search](https://www.imdb.com/search/keyword/), or [IMDb Title Search](https://www.imdb.com/search/title/).

The expected input is an IMDb List URL or IMDb Search URL. Multiple values are supported as a list only a comma-separated string will not work.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  James Bonds:
    imdb_list: https://www.imdb.com/list/ls006405458
    collection_order: custom
    sync_mode: sync
```
```yaml
collections:
  IMDb Top 250:
    imdb_list: https://www.imdb.com/search/title/?groups=top_250
    collection_order: custom
    sync_mode: sync
```
```yaml
collections:
  Christmas:
    imdb_list:
      - https://www.imdb.com/list/ls025976544/
      - https://www.imdb.com/list/ls003863000/
      - https://www.imdb.com/list/ls027454200/
      - https://www.imdb.com/list/ls027886673/
      - https://www.imdb.com/list/ls097998599/
    sync_mode: sync
    collection_order: alpha
```

You can also limit the number of items to search for by using the `limit` and `url` parameters under `imdb_list`.

```yaml
collections:
  IMDb Popular:
    imdb_list:
      url: https://www.imdb.com/search/title/?title_type=feature,tv_movie,documentary,short
      limit: 50
    collection_order: custom
    sync_mode: sync
```

This can be used for multiple lists as seen below.

```yaml
collections:
  Top Action:
    imdb_list:
      - url: https://www.imdb.com/search/title/?title_type=feature&release_date=1990-01-01,&user_rating=5.0,10.0&num_votes=100000,&genres=action
        limit: 100
      - url: https://www.imdb.com/search/title/?title_type=feature&release_date=1990-01-01,&user_rating=5.0,10.0&num_votes=100000,&genres=action&sort=user_rating,desc
        limit: 100
```

You can also find episodes using `imdb_list` like so.

```yaml
collections:
  The Simpsons Top 100 Episodes:
    collection_order: custom
    collection_level: episode
    sync_mode: sync
    imdb_list:
      url: https://www.imdb.com/search/title/?series=tt0096697&sort=user_rating,desc
      limit: 100
    summary: The top 100 Simpsons episodes by IMDB user rating
```