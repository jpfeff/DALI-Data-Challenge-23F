# DALI Data Challenge 22S
## Joshua Pfefferkorn

## Part 1: 

https://public.tableau.com/app/profile/joshua.pfefferkorn/viz/DALIVisualizationsPfefferkorn/ProfitsbyU_S_State?publish=yes

### Visualization 1: Profits by U.S. State

#### Explanation

This visualization is an interactive map of U.S. States and profits. Hovering over a state displays total profit or loss in that state in USD. Clicking a state reveals its profits by sub-category and profits over time. States colored green indicate prositive profits, while those colored red have not been profitable. When no state is selected, aggregate data is shown. Hovering over either of the lower visualizations displays total profits in USD for the specified sub-category or time point.

#### Analysis

Aggregate data indicates that tables, bookcases, and supplies all account for a net loss. Furthermore, profits in various midwestern and eastern status are negative. On the contrary, profits are high in states like California, New York, and Washington. Even so, tables still result in a loss in these states. I also noticed that profits seem to exhibit some seasonality, with profits appearing to peak around fall or winter months. A store manager could use these visualizations to adjust sales (in terms of season, category of goods, and region) to maximize profit.

### Visualization 2: Sales by U.S. City

#### Explanation

This visualization, another interactive map, shows sale distribution across cities in the U.S. Larger dots correspond to a greater portion of sales; hovering over a dot shows total sales in USD, and clicking it updates the graphs below. The lower visualizations decompose sales into category (left) and segment (right). Hovering over either of these visualizations displays total sales in USD.

#### Analysis

This visualization indicates that sales are highest in large coastal cities like Los Angeles, San Francisco, Seattle, New York City, and Philadelphia. Sales are much more sparse in Midwestern and Great Plains regions. The cities vary in terms of segment and category breakdown. This visualization provides valuable information; for example, a store owner could use this to target more specific advertisements in high-sale cities based on segment and category data, or perhaps to increase advertisement effort (or cut it off entirely) in low-sale regions.

### Visualization 3: Sub-Regional Profits and Shipping Time in the U.S.

#### Explanation

This visualization functions like the previous two, but divides U.S. states into sub-regional groups rather than state or city. Clicking on any sub-region displays its profit margin ratio accompanied by a trend line. On the right, average time to ship to the selected subregion is displayed.

#### Analysis

This visualization combines the metrics in the previous two, using profit margin ratio computed with sales and profit data. Trendlines indicate general tendencies in earning proportions. This metric is useful because it displays profit normalized by sales, so profit magnitude is not just a function of the number of sales. The map is broken down into broader sub-regions, allowing for a higher-level overview of regional trends. As shown, sales in the West, North West, and North East have high profit margin ratios as well as a upwards trendline. Overall, profit margin in the South is negative or trending downwards. Profit margins in the Midwest and Mid-Atlantic are slightly positive, and relatively stationary in terms of trend. This visualization could be used by the store to inform marketing efforts in these regions.

## Part 2:

#### Explanation

For this part of the challenge, I used Pandas dataframes to pre-process the data, Seaborn to create a brief visualization section, and TensorFlow with Keras to train a model to predict profit margin ratio given a sale. Comments and markdown cells in the notebook describe my process of cleaning and investigating the data.

#### Visualizations

Here, I used Seaborn to visualize profits and sales over three divisions: segment, sub-category, and state. As indicated by my Part 1 visualizations, profits were negative in various sub-categories and states. I also observed feature correlations using a correlation heatmap. I found that discount percentage was highly related to profits, and that losses seemed to begin around a 20% discount. I suspected that item type and sub-category also related strongly to profit. -

#### Data Preprocessing

Given my plan of creating a model to predict profit margin ratio, I processed the data first by dropping columns that were unnecessary. First, Row ID and Order ID, identification elements for past sales, were not needed. Customer data also seemed extraneous, so I dropped Customer ID and Customer Name as well. Finally, I dropped Country because all sales were from the U.S.

Next, I went about transforming Order Date and Ship Date into more useful data forms. I split the dates by day, month, and year, and created new float-type feature columns for each of these. Next, I transformed categorical features like Segment, Region, and Category into one-hot-encoded columns so that the model could correctly process them. I also added a new, computed column -- Profit Margin Ratio -- and dropped the Sales and Profit columns.

#### Model

I opted to use a Tensorflow Sequential model given its adaptability and customization options. After splitting the data into test and train sets and shuffling it, I designed the model. I chose two Dense layers with 128 units and a ReLu activation function and a fully-connected linear layer, which I found to be optimal after several iterations of tuning and testing. Training the model, I chose a validation set size of 20% to avoid overfitting. I opted for 100 epochs, since the cost seemed to converge the lowest around that point. I also enabled a feature that reduces the learning rate when cost begins to plateau, allowing for more precise steps towards a minimum. Ultimately, the model performed very well, with a mean squared error of around 0.023 and an R^2 score of about 0.89. This model could be useful for store owners to predict profitability of a sale or to tune discount and sales prices given expected profit.

