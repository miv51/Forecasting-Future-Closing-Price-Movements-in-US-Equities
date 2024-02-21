# Forecasting Future Price Movements in US Equities

Used tree-based and gradient boosting ML methods to predict future price movements of US equities using the dataset from the Kaggle competition - [Optiver: Trading at the Close](https://www.kaggle.com/competitions/optiver-trading-at-the-close/overview). <br>

#### Data Preprocessing and Feature Engineering Steps

* transformed the imbalance flag into three separate flags (one-hot-encoding). One for each of the following: buy imbalance, sell imbalance, and no imbalance.
* added an additional flag that - when true - indicates that a set of inputs contain both the near and far prices.
* added an additional feature: spread (ask price - bid price).
* log transformed the following features: imbalance_size, reference_price, matched_size, bid_price, bid_size, ask_price, ask_size, wap, spread, far_price, and near_price.
* standardized the inputs.
* performed Principal Component Analysis on the inputs to transfrom the highly correlated features into more linearly independent components and reduce noise.

#### ML Model Used
After experimenting with various tree-based and gradient-boosting models, I ended up using a stacked model with two layers - the first containing a set of base models of varying model types and hyperparameters, and the second containing the meta model which takes the outputs from the first layer as its inputs.

#### Results
After evaluating the final model on the validation set ...
