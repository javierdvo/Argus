# Future Work

The scope of this solution is currently limited due to the timeframe for development. Further proposed improvements to the Argus product are as follows: 

## Thorough Research

A much more thorough literature research should be made to fully understand the aggregate conclusions in this field from academia and validate other alternatives and viable solutions. Multiple references should be analyzed and evaluated for the different pieces of the solution before a more definite implementation.

## Robust and comprehensive delimitation

A more in depth delimitation of the solution is preferred. There are certainly many gaps that I haven't seen or thought about, or areas where my proposed solutions are lackluster, inexperienced or inefficient. A more thorough approach to this would require much more thorough discussions with multiple PMs, developers and researchers to ensure this is reviewed by multiple sets of eyes and a good solution can be iteratively achieved.

## Evaluation extension

Multiple evaluation metrics can be extended in the generative model evaluation to provide a more robust and certain evaluation of the validness of the different models. 

## Better documentation and citations

Documentation should be extended with better descriptions, explanations, mathematical Latex equations, and multiple cites from the academic sources used in the system to ground the decisions being made and methods being used.


## Code Implementation

The description of Argus should be implemented in a Proof-of-Concept working demo to prove that it works and start iterating based on actual use of the system. The implementation should follow the description in the architecture to make it robust and scalable from its onset, although a limited PoC can also be executed.

## Dataset collection

Multiple OS datasets should be implemented to validate the potential of this idea and prove that the system works correctly.

## Multimodal Sensors
The current version of Argus is limited to evaluating camera-based models that use images as their input information. Argus can be extended to use additional modes of information that are commonly used in ADAS systems. Different weather effects impact each of these sensors differently, so there are some that make sense to validate and others that won't for each sensor. For the adverse weather effects that do occur, the complexity of implementing this lies in obtaining the adequate datasets (with most being proprietary) that contain both clear weather and adverse weather sensor data that can then enable learning the domain mapping function of each.

## CI & CD
Continuous Integration (CI) and Continuous Delivery (CD) via Jenkins or similar should also be implemented to ensure a smooth and flawless experience from the client's and ensure that the system is reliable, scalable and maintainable over time with faster development cycles. JIRA tracking and Github / Gitlab integrations should be implemented to 

## Scalable infrastructure

The current infrastructure of Argus is limited in its throughput capacity. A production-ready version should be implemented in scalable infrastructure that can easily add extra capacity based on demand and reduce it when unnecessary, to ensure optimal cost that fulfills all the system's needs. Load-balancing, resource allocation balance, and cluster-based computing instances can be possible solutions to help the system scale better based on client demand. The computing cost can also be automated by using Apache Spark, Hadoop, Flink, Dask, dCUDA, etc. Furthermore, code efficiency optimization would also be crucial to ensure the maximum possible efficiency.

## Comparison vs Phenomenological Simulation

Further research needs to be invested in comparing the GAN-based weather simulation with the phenomenological simulation to truly evaluate if the GAN-based approach is adequately good at mapping and in an end-to-end solution to truly be similar in performance to a physics-based simulation, to ensure that there is actual empirical merit to using it as a better alternative.