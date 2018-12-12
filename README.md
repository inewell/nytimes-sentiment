# nytimes-sentiment
A data visualization applying the Python library nltk's VADER sentiment analysis tool to words in today's NYTimes. Check it out at [https://inewell.github.io/nytimes-sentiment/](https://inewell.github.io/nytimes-sentiment/).

I did this project in CSC630: Data Visualization at Phillips Academy for my text project. I selected the topic, found the data, and came to all the conclusions about it myself.

This investigations looks at the current issue of the New York Times, and applies sentiment analysis to it. Sentiment analysis is basically a way of categorizing the feeling beheind a sentence or phrase. Natural language is very complex, and sentiment analysis is a difficult problem. I used the pretrained VADER model from the Python library nltk. This model is trained on social media and, when fed a sentence, outputs a positive, negative, neutral, and compound score for that sentence. I just looked at the compound score, which is a floating-point number between -1 and 1 (1 is very positive sentiment, i.e. "That movie was GREAT!", and -1 is very negative sentiment, i.e. "That movie was HORRIBLE!").

In this project, I looked at a subset of words from the Times, taken to be the 150 most-frequent nontrivial words. I could have probably used a more advanced way of extracting nontrivial words, such as just taking nouns or using something like TF-IDF, but this project doesn't do that. Nonetheless, it yields some interesting results through the following method:

For each of the words, I looked at every sentence that contains it, then applied sentiment analysis to all those sentences. Then I plotted each score on a forced-body diagram based on the average sentiment score and frequency; more frequent words are represented by larger circles, and more positive sentiment is to the right (negative to the left).

It is interesting to see how while some words are always in the paper, others fluctuate constantly day-by-day on account of the top stories of the time. For example, when Paul Manafort was indicted, his name was one of the most frequent words in the Times. Also, some words always tend to be near the ends of the sentiment spectrum; for example, "killed" is almost always the most negative word.

So what was the motivation for this project? Well, the idea of a liberal-biased mainstream media has been thrown around by conservatives for a long time. Now the "fake news" slogan has become ubiquitous as a result of Trump's dictatorial media-bashing. Thus, I wanted to get a data-based sense of how "biased" the New York Times, one of the world's most reputable newspapers, really may be. Now, there are a few caveats to this: a sentiment score could be particularly high or low because of one story, because of errors in the sentiment analysis (actually, it skews positive as it is trained on social media, which is a nasty, negative place), or because of some actual kind of bias. Thus, you have to take the results of this with a grain of salt; they don't really prove anything.

For me at least, this visualization is at least, if not conclusive, fun to explore. Hopefully my audience will enjoy it as well.

## Table of contents
* `text-project.html`: the HTML page that renders this project.
* `NYTimes.ipynb`: the Jupyter notebook that gathers and cleans the data from the NYTimes website. It outputs it into a JSON file.
* `nytimes_sentiment.json`: the data file containing the sentences, URLS, and sentiment analysis results. Outputted by the Jupyter notebook.
* `top_words.json`: the data file containing the top nontrivial words in the NYTimes. Outputted by the Jupyter notebook.

## Authors
* Isaac Newell
