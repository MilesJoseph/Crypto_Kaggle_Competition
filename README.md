
# G-Research Crypto Compeition :moneybag:

### :vertical_traffic_light: Light GBM with Optuna Hyperparameter Tuning and Purged Group Time Series 

The repository that I have put together is for the G-Research Crypto Forecasting on Kaggle. The purpose of the competition is to forecast short term returns in 14 popular cryptocurrencies. The data for the competition goes back to 2018 and outside data is acceptable for this competition.

Some exeprts from the competition page itself;

The simultaneous activity of thousands of traders ensures that most signals will be transitory, persistent alpha will be exceptionally difficult to find, and the danger of overfitting will be considerable. In addition, since 2018, interest in the cryptomarket has exploded, so the volatility and correlation structure in our data are likely to be highly non-stationary. The successful contestant will pay careful attention to these considerations, and in the process gain valuable insight into the art and science of financial forecasting.

G-Research is Europe’s leading quantitative finance research firm. We have long explored the extent of market prediction possibilities, making use of machine learning, big data, and some of the most advanced technology available. Specializing in data science and AI education for workforces, Cambridge Spark is partnering with G-Research for this competition. Watch our introduction to the competition below:

There is a video available for viewing to contextualize the competition.

Some of the main things I have done in this project; 

:rocket: Light GBM - Aside from the submission that everoyne has made at the top of the leaderboard which is noted in the caveat section I have put together an easy to follow Light GBM notebook in the Notebooks section that givve a detailed explanation of the data and algo. 

:electric_plug: Light GBM with GPU boost module - I also have under the notebooks section a notebook that gives a way to use Light GBM with GPU boost as well as an explanation on the module. Since the competition does not allow for internet to be used, I considered bringing in light GBM with GPU as a module from a .tar file but did not end up doing so since the leaderboard is useless, but it gives a good example of how to do so if you wanted. 

:hammer: Optuna - The main EDA and Model notebook also gives an explanation of hyperparameter tuning with Optuna and crossfold 
      

    

## Evaluation

The evaluation of the competition is based on a weighted Pearson Correlation. The weight is defined by Gresearch of individual assets.

More specifically, the correlation is between the predicted and actual targets. 


## Caveats

Unfortunately, the test data is contained in the training data which makes the leaderboard for this competition worthless. This is from Julian Peller;

Below you can see a 18-line submission that overfits the public LB fully, using the fact that the test period is contained in the train data to get the closest point for each test row.

It is not actually leaky because the fact that the LB is part of the public data was publicly disclosed by the organizers. In my opinion, though, the statement was not clear enough regarding the fact that the public LB test period was contained in the train.csv, but I guess it doesn't matter.

I don't know the public test time range, but here I'm assuming that is starts from the placeholder and goes on. The placeholder test.csv starts at '2021-06-13 00:00:00'. I tried with the full train.csv but it takes a long time and it's probably going to fail the submission.

The LB doesn't seem to be meaningful at all as long as we don't know which training data points are leaking into the public test set and which data points are not

So, all in all...kind of a bummer. I didn't realize there was an issue until near the end of my work when I looked at the leaderboard adn saw that the first few hundred people have perfect scores and did one minute of research. 

Very helpful explanations from Julian Peller and much credit is due to him for giving an honest and transparent explantion. 


## Side Note

The read me in the notebooks under the 'notebook' section have extensive explanations of my exploration and model development with particularly detailed explanations of Light GBM.
## Project Organization

The file organization of this project uses Cookie Cutter. Cookie Cutter is a great way to organize data science projects. For kaggle competitions, it ma be a little uneccessary, but it is helpful to get in the practice of using this structure for all personal projects or work.

Noteable places to look in this file structure are the requirements and the notebooks. The notebooks section contains one notebook with the exploratory data analysis as well as model development. The second notebook has Light GBM with GPU boost.

An explanation for why each of these notebooks are needed seperately is simple. The EDA and model notebook in the rules of this competition can not use the internet. Since we are using kaggle noteboks we have the internet option turned off in this notebook. At the time of writing this we are still testing with the additional notebook pertaining to Light GBM with GPU. This notebook downloads Light GBM with GPU and creates a .tar file. Ideally, I can import this .tar file as a module ithin the main model notebook to expedite the training time.


## Acknowledgements

Each of the notebooks in the notebook section have acknowledgements for the notebooks that I took inspiration from. 


## Improvements and Next Steps

I need to improve on the main EDA and modeling notebook. Naturally, I would like to move up in the leaderboard with a model that does not include the test data within the training data. I think around 500 people have included the test data in the train data in their training so nearly everyone ahs a perfect score. 

Better documentation and run time will be required, so we could try to implement the GPU module and do some more work on feature engineering. 
## Authors

- Miles Klingenberg

References to; 

- Julian Peller 