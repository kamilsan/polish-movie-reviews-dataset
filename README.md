# Polish movie reviews dataset

Dataset of short movie reviews written in Polish. Data was sources from [Filmweb](https://www.filmweb.pl/) using undocumented API. It contains 29066 reviews of 12709 unique movies written by 61 movie critics. Review length is capped to 160 characters by Filmweb.

Some may find it useful to experiment with sentiment analysis or recommendation system models.

## Data format 

```json
{
    "reviews": [
        {
            "user_id": 13,
            "movie_id": 9268,
            "review": "Wielka niespodzianka i najbardziej oryginalny film z Rumunii od dekady.",
            "rating": 9
        },
        // ...
    ]
}
```

Where `rating` is a number from 1 to 10. Please note that ids **do not** correspond to original ids from Filmweb's dataset. 

Some steps were taken to filter unusable data (empty reviews, links, etc.), but this dataset in definitely not perfectly clean and has some issues. For examples, some reviews leak scores:

```json
{
    "user_id": 15,
    "movie_id": 531,
    "review": "7,5 | Smutne i autentyczne",
    "rating": 7
}
```

Those should probably be filtered before training on model for sentiment analysis.