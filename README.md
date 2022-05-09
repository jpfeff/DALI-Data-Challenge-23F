# DALI Data Challenge 22S
## Joshua Pfefferkorn

## Part 1: 

https://public.tableau.com/app/profile/joshua.pfefferkorn/viz/DALIVisualizationsPfefferkorn/ProfitsbyU_S_State?publish=yes

### Visualization 1: Profits by U.S. State

This visualization is an interactive map of U.S. States and profits. Hovering over a state displays total profit or loss in that state in USD. Clicking a state reveals its profits by sub-category and profits over time. States colored green indicate prositive profits, while those colored red have not been profitable. When no state is selected, aggregate data is shown. Hovering over either of the lower visualizations displays total profits in USD for the specified sub-category or time point.

### Visualization 2: Sales by U.S. City

This visualization, another interactive map, shows sale distribution across cities in the U.S. Larger dots correspond to a greater portion of sales; hovering over a dot shows total sales in USD, and clicking it updates the graphs below. The lower visualizations decompose sales into category (left) and segment (right). Hovering over either of these visualizations displays total sales in USD.

### Visualization 3: Sub-Regional Profits and Shipping Time in the U.S.

This visualization functions like the previous two, but divides U.S. states into sub-regional groups rather than state or city. Clicking on any sub-region displays its profit margin ratio accompanied by a trend line. On the right, average time to ship to the selected subregion is displayed.

## Part 2:

For this part of the challenge, I used Pandas dataframes to pre-process the data, Seaborn to create a brief visualization section, and TensorFlow with Keras to train a model to predict profit margin ratio given a sale. Comments and markdown cells in the notebook describe my process of cleaning and investigating the data. The model's final error was around 0.023, with an R^2 score of 0.89.
