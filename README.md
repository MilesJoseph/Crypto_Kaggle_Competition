## Crypto Competition 

 ```The repository that I have put together is for the G-Research Crypto Forecasting on Kaggle. The purpose of the competition is to forecast short term returns in 14 popular cryptocurrencies. The data for the competition goes back to 2018 and outside data is acceptable for this competition.```
	
```Some exeprts from the competition page itself;```

```The simultaneous activity of thousands of traders ensures that most signals will be transitory, persistent alpha will be exceptionally difficult to find, and the danger of overfitting will be considerable. In addition, since 2018, interest in the cryptomarket has exploded, so the volatility and correlation structure in our data are likely to be highly non-stationary. The successful contestant will pay careful attention to these considerations, and in the process gain valuable insight into the art and science of financial forecasting.```

```G-Research is Europe’s leading quantitative finance research firm. We have long explored the extent of market prediction possibilities, making use of machine learning, big data, and some of the most advanced technology available. Specializing in data science and AI education for workforces, Cambridge Spark is partnering with G-Research for this competition. Watch our introduction to the competition below:```
	
```There is a video available for viewing to contextualize the competition.```
	
## Evaluation

```The evaluation of the competition is based on a weighted Pearson Correlation. The weight is defined by Gresearch of individual assets.```

## Caveats 

```Unfortunately, the test data is contained in the training data which makes the leaderboard for this competition worthless. This is from Julian Peller;``` 

```Below you can see a 18-line submission that overfits the public LB fully, using the fact that the test period is contained in the train data to get the closest point for each test row.```

It is not actually leaky because the fact that the LB is part of the public data was publicly disclosed by the organizers. In my opinion, though, the statement was not clear enough regarding the fact that the public LB test period was contained in the train.csv, but I guess it doesn't matter.```

```I don't know the public test time range, but here I'm assuming that is starts from the placeholder and goes on. The placeholder test.csv starts at '2021-06-13 00:00:00'. I tried with the full train.csv but it takes a long time and it's probably going to fail the submission.```

```The LB doesn't seem to be meaningful at all as long as we don't know which training data points are leaking into the public test set and which data points are not```
	
Project Organization
------------
```The file organization of this project uses Cookie Cutter. Cookie Cutter is a great way to organize data science projects. For kaggle competitions, it ma be a little uneccessary, but it is helpful to get in the practice of using this structure for all personal projects or work.``` 
    
```Noteable places to look in this file structure are the requirements and the notebooks. The notebooks section contains one notebook with the exploratory data analysis as well as model development. The second notebook has Light GBM with GPU boost.``` 
    
```An explanation for why each of these notebooks are needed seperately is simple. The EDA and model notebook in the rules of this competition can not use the internet. Since we are using kaggle noteboks we have the internet option turned off in this notebook. At the time of writing this we are still testing with the additional notebook pertaining to Light GBM with GPU. This notebook downloads Light GBM with GPU and creates a .tar file. Ideally, I can import this .tar file as a module ithin the main model notebook to expedite the training time.```

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
