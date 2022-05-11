# DALI Data Challenge 22S
## Joshua Pfefferkorn

## Part 1: 

https://public.tableau.com/app/profile/joshua.pfefferkorn/viz/DALIVisualizationsPfefferkorn/ProfitsbyU_S_State?publish=yes

### Visualization 1: Profits by U.S. State

#### Explanation

This visualization is an interactive map of U.S. States and profits. Hovering over a state displays total profit or loss in that state in USD. Clicking a state reveals its profits by sub-category and profits over time. States colored green indicate prositive profits, while those colored red have not been profitable. When no state is selected, aggregate data is shown. Hovering over either of the lower visualizations displays total profits in USD for the specified sub-category or time point.

#### Analysis

Aggregate data indicates that tables, bookcases, and supplies all account for a net loss. Furthermore, profits in various midwestern and eastern status are negative. On the contrary, profits are high in states like California, New York, and Washington. Even so, tables still result in a loss in these states. A store manager could use these visualizations to adjust sales -- in terms of categories of goods and regions of the U.S. -- and maximize profit.

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

For this part of the challenge, I used Pandas dataframes to pre-process the data, Seaborn to create a brief visualization section, and TensorFlow with Keras to train a model to predict profit margin ratio given a sale. Comments and markdown cells in the notebook describe my process of cleaning and investigating the data. The model's final error was around 0.023, with an R^2 score of 0.89.


