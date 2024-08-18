# CAP: Causal Air Quality Index Prediction Considering Neighbor Intervention.
  This repository contains codes for a causal AQI prediction approach that introduce a causal framework that employs the front-door adjustment to explicitly eliminate unmeasured confounders by intervening in industrial emissions from the target enterprise. Meanwhile, we take industrial emissions of neighboring enterprises into account when intervening in the target enterprise and simulate the dispersion of industrial emissions through a Gaussian plume model based on meteorological factors. The overview of our approach is illustrated in the main paper. The methods are described in this paper.
# Installation
Our code are divided into four parts:  
    1.modeling P(X,X_{nei})
