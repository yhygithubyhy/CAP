# CAP: Causal Air Quality Index Prediction Considering Neighbor Intervention.
  This repository contains codes for a causal AQI prediction approach that introduce a causal framework that employs the front-door adjustment to explicitly eliminate unmeasured confounders by intervening in industrial emissions from the target enterprise. Meanwhile, we take industrial emissions of neighboring enterprises into account when intervening in the target enterprise and simulate the dispersion of industrial emissions through a Gaussian plume model based on meteorological factors. The overview of our approach is illustrated in the main paper. The methods are described in this paper.
# Installation
Our target is defined as:  

$p(Y|do(X,X_{nei}),W)=\int_{m}p(M|X,X_{nei},W)\,dM\int_{x}\int_{x_{nei}}p(Y|X,X_{nei},M,W)p(X,X_{nei})\,dXdX_{nei}.$  

Therefore, our code contains four parts:  

1. modeling $p(X,X_{nei})$;
2. modeling $p(M|X,X_{nei},W)$;
3. modeling $p(Y|X,X_{nei},W,M)$;
4. estimating $p(Y|do(X,X_{nei}),W)$.

To run the code, please clone this repository. You need to install the environments: `Python 3` including the packages `numpy` ,`pandas` and `tqdm`.
# Dataset format

1. PM<sub>2.5</sub>-CQW dataset: It covers PM<sub>2.5</sub> industrial emission data (enterprise name, enterprise address, enterprise emission) from more than 300 enterprises in 12 districts and counties in the western part of Chongqing, as well as air quality data (district name, address of the air quality monitoring station, AQI) and meteorological data (wind direction, wind speed) from 12 districts and counties. All data were collected hourly and for the whole year of 2022 (from Jan. 1, 2022 to Dec. 31, 2022).

2. SO<sub>2</sub>-CQE dataset: It covers SO<sub>2</sub> industrial emission data (enterprise name, enterprise address, enterprise emission) from more than 100 enterprises in two districts and counties in the eastern part of Chongqing Municipality, as well as air quality data (district name, address of the air quality monitoring station, AQI) and meteorological data (wind direction and speed) from the two districts and counties. All data were collected at the same hourly rate as PM<sub>2.5</sub>-CQW dataset for the entire year 2022 (from Jan. 1, 2022 to Dec. 31, 2022).

# Usage

1. Run the file `main.py` to train the model.
```
python main.py -train True
```

2. Run the file `main.py` to evaluate the performance of the model.
```
python main.py -valid True
```
3. Run the file `main.py` to predict potential AQI.
```
python main.py -predict True
```
