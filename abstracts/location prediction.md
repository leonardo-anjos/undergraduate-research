## location prediction: a deep spatial tempotal learning form external sensors data 


### 1. introduction 

in general, the mobility prediction problem consist in inferring the next relevant location of a moving object based on historical information and its most recent traking

in three levels of mobility prediction are considered:
- (1) object position
- (2) path prediction 
- (3) next place prediction

in levels 1 and 2, usally, the models learned from raw trajectories obtained by global position system (gps) devices, and their predictions consider the movement of the object

level 3 predicts stops rather than movements, usually bt leaning form sequence of points of interest or georeferenced events

recurrent neural networks (rnn) are one of the most efective approaches to predict sequenced data as they can learn the relationship between consecutive values in a sequence


### 2. problem statement

to example, are used data from sensors are imperfect and thus produce incomplete trajectories with missing data.

- follow some definitions to support our problem statement
#### definition 1: external sensor observation
when an external sensor registers the passage of a moving object 'm' at time 't', it produces a tuple 'o = (m,s, t)'.
however, the sensors may fail to capture the passage of a moving object 

#### definition 2: external sensor trajactory


### 2.1 characteristics of external sensor trajctories

diferent from classifcation problems with many classes, to learn from trajectories we have to consider complex transitions patterns and time-dependence. as the sensors have spatial relationships among them, the proximity of the predicted value to
the actual registered value is also important. furthermore, the trajectories obtained from external sensors have several particularities that provide new opportunities while raising some challenges

- (1) huge data 
sensors continuously capture a massive number of observations per day. the application needs to ingest multiple sensors data streams, compute the last observations of the moving object and make predictions online. the complexity to manage these tasks increases with the number of vehicles.

- (2) exhaustive types of trajectories 
moving objects are not restricted to a specifc feet of vehicles as usual in gps data collection. commuters, a feet of taxis or buses, deliveries, etc., are all tracked by the road-side sensors. thus, trajectories can have very diferent patterns. for example, commuters usually have temporal repetitively behavior like go to work and return home every week-day; on the
other hand, taxis may have very diferent behaviors that depend on their passengers

- (3) sparsity
the roads of the city. The complete tracking of moving objects is not available, and the reported positions per trajectory are very sparse in space and time. the sparsity returns the trajectories shorter and with fewer data points, making the prediction harder

- (4) incompleteness and uncertainty
sensors may fail to capture the passage of a vehicle, producing incomplete trajectories

#### finally, we assume that EST is constrained by the topology of the network; this may help to compensate the sparsity and incompleteness of the trajectory observations

