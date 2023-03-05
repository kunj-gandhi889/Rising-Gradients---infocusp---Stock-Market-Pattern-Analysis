# Rising-Gradients---infocusp---Stock-Market-Pattern-Analysis
Stock market analysis is getting popular as more people are trying their hands on with Stocks. In such trading, chart pattern studies play a large role during technical analysis. When data is plotted
there is usually a pattern which naturally occurs and repeats over a period. And such things could help you understand the market and do some predictive analysis to get the trend.
### Problem details

You will be given sample time series data and corresponding annotation that denotes where and
which pattern exists (in the given data) to train the algorithm and to visualize the data / patterns.
Your job is to identify such patterns in the test data.
### Step-by-step guide to run program
To Run the Program, the user must have python/anaconda environment installed. (>3.8 version)
Python Essential Library Installation for running program
1. Pandas
2. Numpy
3. opencv-python (cv2)
4. plotlty / dash
5. matplotlib
6. Random, datetime and os modules
7. Keras and Tensorflow

inorder to understand this project better, the user must have basic of stock market data representation i.e candlesticks and patterns present in them.
#### Understand Stock Market Data Representation : https://www.investopedia.com/terms/c/candlestick.asp 
#### Understand Stock Market Pattern : https://www.cmcmarkets.com/en/trading-guides/stock-chart-patterns

### Steps
1. We are representing the data of day in form of candlestick data which is visualize better using plotly since the data is in time series format.
2. Any data having 'open', 'high', 'low', 'close' and 'date' & more can be plotted and visualize using this representation.
3. Generally the data is in form of csv file sampleData, which contains stocks info every 5 minutes from 9:00 AM to 3:00 PM (some irregularties exist which we have find using irregular() function)
4. The Pattern information is in another csv file sampleDataGT which contains starttime and endtime of 1 out of 4 patterns. ('Head and Shoulders' ,'Reverse Head and Shoulders', 'Double Top','Double Bottom')
5. We are saving images of every pattern formed and creating some 'no pattern' random candlestick images and storing them all in seperate directory.
6. Then we are cropping only important region of image, reshaping into smaller dimension and converting into grayscale images, so CNN model can work better.
7. Then we are creating features and labels from images stored in all image patternType directory and then splitting the data into training and testing.
8. Then we are creating a CNN architecture which can learn the patterns from images, we have used transfer learning to train VGG16 on imagenet weights.
9. Then we are predicting the patternType for every day.

### Functions Used
1. draw_candlesticks() -> It draws the candlesticks and saves if given parameter True.
2. highlightPattern() -> It highlights the pattern from sampleDataGT file in sampleData File and return Dataframe which contains the pattern from start and end
3. processImage() -> It crops, resize and converts candlestick image to grey scale image.
4. randomData() -> It generates random data from dataframe that are not forming any patterns
5. predictPattern() ->  Main Function , that takes any input dataframe and processes all steps to produce output dataframe that contains which pattern formed no which day 
