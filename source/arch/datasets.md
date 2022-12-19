# Datasets

Datasets are the core of any ML system. They are the source of truth for the system to learn from, and thus the quality of the dataset is the most important factor in the quality of the system. Datasets are also the most expensive part of the ML system, as they are the most time consuming to collect and the most costly to obtain. It is important to ensure that the dataset is representative of the problem that the model is being trained to solve, and that it has been cleaned and preprocessed to remove any errors or inconsistencies. Thus there is a pressing need to use a clean, representative and large ADAS dataset for training and validation of generative and evaluation models. The selection of datasets is crucial for the success of Argus.

## Open Source Datasets

Open Source datasets are mostly useful for Proof of Concept and simple validation that the system works correctly (and thus would work with a proprietary dataset). Most datasets that are open source are made available under non-commercial use terms, and as such can't be used in products that are meant to be sold

Some of the OS datasets that can be used for research purposes are the following:

- [Cityscapes](https://www.cityscapes-dataset.com/)
- [KITTI](https://www.cvlibs.net/datasets/kitti-360/)
- [BDD100K](https://www.bdd100k.com/)
- [NuScenes](https://www.nuscenes.org/)
- [A2D2](https://www.a2d2.audi/a2d2/en.html)
- [Apolloscape](https://apolloscape.auto/)
- [comma2k19](https://github.com/commaai/comma2k19)
- [ImageNet](https://www.image-net.org/)


## Proprietary Datasets

The use of proprietary datasets is ideal from a legal standpoint as there are no limitations to its financial usage, but are complex to obtain and are highly costly. A fleet of vehicles needs to be setup with sensor rigs and those vehicles then need to be driven in diverse environments. The dataset is then restricted by the locations and conditions that are accessible to the fleet of driving vehicles. In multiple countries recording vehicles need to obtain legal rights to record their environment and can be limited in the scope of the data collected.

## Client Datasets

The use of datasets that clients have collected is promising as it offloads the cost and legal implications of dataset collection unto the client, but for the same reasons is the most complex to obtain. Its highly unlikely that a client will allow unrestricted access to their dataset for use by another party (as datasets grant a competitive advantage), and sometimes the legal implications straight do not allow this.

## Third-party Datasets

Third party datasets can also be explored, but those definitely involve an economical cost. Still, it might make financial sense to use a third-party dataset if its cost is smaller than the cost of collecting the data yourself. 

## Simulated Datasets

Tools like [Nvidia DRIVESim](https://developer.nvidia.com/drive/simulation) and [Parallel Domain](https://paralleldomain.com/) can be used to generate synthetic datasets that can be used for training and validation. The main advantage of using synthetic data is that its cost is much lower, it tends to be deterministic and it can be generated in a controlled environment, and thus can be used to test the system in scenarios that are not possible in the real world. The main disadvantage is that the data is not real, and thus the system might not generalize well to the real world depending on the simulation engine.

There is a risk that using simulated datasets for the generative models won't really cross the sim-to-real gap, as it can generate erroneous a priori biases in the data that match the simulation and erroneously appear to be reliable. Thus, simulated datasets should be used as a last resort.