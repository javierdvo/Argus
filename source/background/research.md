# Previous Research

This will mainly analyze the findings of [Multi-weather city: Adverse weather stacking for autonomous driving by Musat et al](https://openaccess.thecvf.com/content/ICCV2021W/AVVision/papers/Musat_Multi-Weather_City_Adverse_Weather_Stacking_for_Autonomous_Driving_ICCVW_2021_paper.pdf). A more thorough and comprehensive analysis of the academic literature is desired though.


## Scope
The authors propose a GAN-based simulation pipeline to generate synthetic images from clear images that have multiple variations based on different adverse weather conditions (Thus obtaining 7 synthetic images from a given real image)

The weather conditions to simulate are rain, night, snow, and rain droplets (plus the mix of droplets+one of the other conditions).


## Main Findings

The authors prove that a modular GAN-based synthetic data simulation pipeline can generate useful synthetic data from clear weather images and that this synthetically-augmented dataset can then be used to improve AD tasks.

The use of multiple generated conditions for training rather than a single generated condition gives the best results in OD and segmentation tasks.

## Datasets

The generative networks are trained on the Cityscapes dataset, as well as Oxford RobotCar, Dark Zurich and, RainyScreens. Then, they are evaluated in the Mapillary, BDD100K, DAWN and ACDC datasets to evaluate how useful are GAN-generated synthetic datasets at improving OD and segmentation tasks.

The datasets present an interesting challenge as the number of samples in some particular combinations (hence highlighting the dimensionality/ data acquisition challenge this actually wants to solve )

## Evaluation

The synthetic data generated from the GANs are evaluated in terms of quality with the Frechet Inception Distance (FID) and Inception Score (IS), and quantitatively by using pre-trained OD and segmentation models (Detectron2) fine-tuned with the resulting synthetically-augmented Cityscapes dataset and then evaluated with the out-of-distribution testing datasets


## Results
The results from the qualitative testing show that the synthetically generated images that results from applying the trained GANs on the testing dataset show potential at detection and segmentation tasks.

The results from the quantitative show that the fine-tuned synthetic datasets for a particular weather condition do not see an important increase w.r.t. the baseline, but that when fine-tuning with all conditions it improves well enough. This suggests that the single-condition overfits towards that condition and worsens the other ones. This also seems to have a beneficial effect in the baseline too, obtaining better results when testing on the cityscapes test and using the synthetically-augmented dataset for training.

Additionally, the results from both tests are consistent with each other as low (good) ranking FID classes also perform well in the actual OD and segmentation tasks, thus reinforcing the underlying hypothesis.

## Notes

The mapping of the droplet adherent is limited to being trained on 
$ (clear, overcast, daytime) -> (droplet,overcast,daytime) $ and is then used for $ (clear, X, X) $. A more thorough solution would be to obtain each mapping for each weather/lightning condition, although this risks an exploding complexity. Alternatively, the GAN can be trained on a diverse dataset that consists of non-droplets and droplets from multiple weather/lightning conditions (ideally balanced). This can be difficult to obtain due to the aforementioned dataset bottleneck

Care should be taken to implement the pipeline completely to each image in the desired dataset, as differing copies per image could cause the augmented dataset to have overrepresented samples that are overfitted towards.

Using the pre-trained Detectron2 (already trained on Cityscapes) and then fine-tuning it to Cityscapes risks overrepresenting samples (but would not impact the testing results as it is done with out-of-distribution samples, i.e. no a priori bias)

