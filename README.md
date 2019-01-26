# fungi-machinelearning-dataset

Machine learning dataset for fungi native to Sweden

## Background
Sometime in the early 2000's I took it upon myself to create a searchable fungi database. I compiled data for about 800 fungi by manually entering information from 2 different sources: ***Svampar i skog och mark - Bo Nylén*** and ***Svampar - en fälthandbok - Svengunnar Ryman and Ingmar Holmåsen***.

The data was included in the software **SvampCentralen**, distributed on CD. I sold this software for a couple of years, but it didn't sell very well and after a few years the project was abandoned.

As time went by, the source code and database was lost to me, and for over 10 years I thought that I had no remaining copies of it. But in late September 2018 I came across a hard drive that hadn't been used for years, and on it I found both the source code and the database. I immediately started trying to extract the data into a format that could be used for machine learning, an area of expertise that I've been increasinly interested in the last few years.

## Data format
The original database consisted of a little more than 800 species, each described by up to 35 attributes. A JSON representation of this original data can be found in the file **data/fungi-original.json**. It consists of several different types of attributes: enumerations, sets and color ranges etc.

For machine learning purposes, this data was then used to create 100 samples of each species with a random distribution of attributes among the possible values. E.g. for the cap color of an Amanita virosa, a random color between bright red and pale yellow was selected, since that was the color range of the original dataset. This data is intended to mimic 100 descriptions of each species, as described by an observer of a sample.

The machine learning optimized dataset can be found in **data/fungi-ml.txt**, where the last column denotes the index of the species. To get the latin name of the species, the index needs to be crossreferenced with the data in **fungi-original.json**.

## Jupyter Notebook
A Jupyter Notebook that loads the dataset and performs an accuracy test of it it also included in **jupyter/fungi-dataset-naive-bayes.ipynb**. The accuracy score is around 95-96%, which looks promising to me even if it's all hypothetical for now.

## Usage
My intention was to build a new web page around this dataset, where users could describe a fungi that they've found and then get a list of possible matches. But since the dataset was created in September 2018, other projects have kept me occupied and in the foreseeable future I will not work any more on this. I'm publishing it since it may be useful for someone else, both for theoretical and practical purposes.

If you have any questions about this dataset, please create an issue here on Github, or contact me at **bighatsmallfeet at gmail . com** and I'll try to help the best I can.
