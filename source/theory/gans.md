# GANs and CycleGANs


Generative Adversarial Networks (GANs) are a type of machine learning model that is made up of two neural networks: a generator network and a discriminator network. The generator network is trained to generate new, synthetic data that is similar to a dataset that it has been trained on. The discriminator network is trained to determine whether a given sample is real or synthetic, based on the dataset it has been trained on.

During training, the generator and discriminator networks are pitted against each other in a two-part "game." The generator network tries to generate synthetic data that is similar enough to the real data that the discriminator network can't tell the difference, while the discriminator network tries to correctly identify whether each sample is real or synthetic. As training progresses, both networks become better at their respective tasks, until the generator network is able to generate synthetic data that is virtually indistinguishable from the real data. This is represented in the following equation as a minimax game: 

$$\min_G \max_D \vec{E}_{x \sim P_\text{real}} \left [ \log D(x) \right ] + \vec{E}_{z \sim P_G} [\log ( 1- D(G(z)))]$$

CycleGANs (short for Cycle-Consistent Generative Adversarial Networks) are a variant of GAN that are specifically designed to perform image-to-image translation tasks. In other words, CycleGANs are used to transform images from one domain into images in another domain while maintaining the same content and structure. An example of this would be transforming an image under clear weather conditions to one the same one as it would appear under  adverse weather conditions (yet maintaining the environment data)

One of the key features of CycleGANs is their use of cycle consistency loss, which helps to ensure that the generated images are not only visually similar to the target domain, but also preserve the content and structure of the original images. This is achieved by training the CycleGAN to translate images back and forth between the two domains and using a loss function that measures the difference between the original image and the translated image.

## Usage

Within Argus, GANs are used in the generation phase of the model evaluation pipeline. Multiple GAN models are trained by the Argus team, and are then used in the dataset augmentation process to generate the adverse weather data for model evaluation. These models are constantly updated based on new data and then evaluated to always provide the best possible results that correctly match. You can select multiple models according to your needs, thereby augmenting your dataset to be augmented with hard-to-obtain adverse weather images and enabling a more robust model validation at a scale.

One of the key benefits of GANs and CycleGANs is that they help tackle the Sim-to-Real gap innately thanks to is discriminator/generator architecture. A GAN with a robust dataset that adequately converges will by definition maximize the closeness of simulated images to real-world images, thus reducing the gap and ensuring the models are validated with real-like data(or the synthetic images can be used for training and thus the model is trained to match real-like probability distributions).

## Cost-effective 

GAN's that have adequately learned the domain mapping from a "clean" image to a adverse weather one (whichever effect it is), have the benefit of being more efficient and cost-effective than phenomenological simulation, given that the underlying probabilistic model that has been trained is sufficiently representative of the actual changes due to the physical phenomena. 

Effectively, the GAN model can bypass the compute-intensive calculation by "learning" an efficient (i.e. densely encoded) mapping of the domain shift in its training step, which can then be easily ran in a new image or scenario at a low computational cost. The phenomenological model necessarily needs to run compute-intensive tasks for each single frame every time it is run. When the number of frames / recordings needed lies in the millions, it might make more economical sense to use the pre-trained GAN.