# Adverse-Weather impact on ADAS

Adverse weather conditions, such as heavy rain, snow, fog, or sandstorms, can significantly impact the performance of camera-based Advanced Driver Assistance Systems (ADAS). These systems rely on cameras to capture images of the surrounding environment and use computer vision algorithms to interpret and analyze the data.

In poor weather conditions, the visibility of the camera may be reduced, which can lead to a decrease in the accuracy and reliability of ADAS systems. For example, if the camera is unable to clearly see the road or other objects due to heavy rain or snow, it may not be able to accurately detect and classify objects, leading to a higher rate of false positives or false negatives. Adverse weather conditions can also cause reflections on the camera lens, which can distort the image and make it difficult for the ADAS to accurately interpret the data.

Adverse weather can significantly impact the performance of camera-based ADAS systems, leading to a decrease in their effectiveness and reliability. It is important for developers and engineers to be aware of these limitations and create systems that correctly function under such adverse conditions.

## Main Adverse-Weather conditions

These conditions (not fully comprehensive) can negatively impact the performance of cameras:

- Night: Low illuminance, reduced detection range, reduced color range, high contrast from other vehicle lamplights.
- Cloudy: reduced illuminance.
- Rain: reduced illuminance, reflective areas,stochastic localization of puddles.
- Snow: high contrast, occluded markings, stochastic localization of snow.
- Sandstorm: very low visibility.
- Smoke: very low visibility.
- Fog: diffuse low illuminance, highly diffused from other vehicle lamplights.

Additionally, the camera sensor can be blocked /occluded by:
- Raindrops
- Mud
- Snow  

## Adverse weather combinations

Weather-generated conditions can be combined between each other (Rain droplet occlusion can be present or not on a rainy day)

Due to the nature of weather effects, some of them are exclusive with each other (One cannot have rain falling on a clear day,) which limits the combinatorics explosion and simplifies the simulated feature space. 

Additionally, some phenomena are limited geographically or temporally (a client selling vehicles only in Dubai is unlikely to need evaluation of snow environments in the same way as a Norwegian company won't need to test sandstorms)

## Impact on ML

As ML models are based on analyzing data from a given input source, if this input source differs from the expected data that it was trained from it has the potential of misclassifying / miscalculating the desired output, and can cause a downstream error due to an erroneous classification leading to an incorrect action being taken.

The increasing dependency (based on the usefulness of ML) of ADAS systems on ML-based systems opens this avenue for potential failure into the system and as such its highly desirable to make the ML models as robust as possible

## Solutions

Hardware-based solutions are one partial, possible solution for this. By making sure the input is as clean as possible, downstream errors due to erroneous inputs can be avoided. This cannot solve all possible adverse weather phenomena as some can't be fixed within the physical boundaries of the vehicle (such as snow covering a lane marker). Alternative sensors are also explored as viable solutions for some of these problems (such as Radars and Lidars) but some present their own challenges, and tend to be more expensive.

Software-based solutions are thus being explored. The main issue with ML models is that they are intrinsically limited in their decision-making process by what they have been trained upon. Thus if a ML model has never been trained in adverse-weather scenarios its performance in the real world under those conditions cannot be known beforehand and the odds of an issue occurring are likely. Thus the main software-based solution has been to increase the training dataset (as well as related evaluation and testing) to also include these scenarios and thus preemptively select those models that perform well under all conditions.

The problem arises due to the fact that obtaining this data is nontrivial and expensive. Most of these conditions cannot be predicted beforehand, and occur on limited dates thus complicating the data-collection process at sufficiently large scales to correctly compensate it (this also exacerbates the class-imbalance problems of ML). Thus the dataset-collection part of ML becomes the bottleneck to solve. 

Simulation has been constantly proposed as a plausible alternative to generate synthetic data that is real-like and can be used to artificially augment the datasets to enhance it and compensate for this bottleneck(it comes with its own set of challenges, which will be further explored). 

