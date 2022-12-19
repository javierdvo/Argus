# Client-Facing

Argus fulfills the following client goals in its client-facing functionality:

- Robustly validate and evaluate the performance of ML models at a scale with synthetically-augmented data.
- Have access to constantly-evolving, state-of-the-art generative models with zero friction.
- Visualize the evaluation of ML models, both qualitatively and quantitatively.
- Visualize the development and improvement of ML models over time to prove the newer versions are indeed optimal and observe trends.
- Be simple to use yet allow customization when required for fine-tuning.
- Quick aggregate identification of failure scenarios / conditions that require further work and focus.
- Complex / Edge case detection and monitoring over multiple model versions. 
- Test dataset cleanup and sanitization.
- Model Explainability.
- Synthetic augmentation of Datasets to extend the training dataset with care and empower the best-performing real-world facing models.

The overarching goal of Argus for the client is to enable simple, yet thorough validation with a one-click or one-line-of-code that accomplishes this. This allows developers to fully focus on their algorithms while trusting that a thorough and complete validation always checks their model performance.

## How we accomplish this

Each Argus client has access to their own client view, where they can

- Select or upload a proprietary Testing Dataset (and its ground truth) for use in the model evaluation.

- Select or upload a proprietary Dataset for use in the Synthetic image generation for dataset augmentation

- Select and use existing Sample Test Datasets to test out model evaluation and synthetic dataset augmentation.

Upon selection of a Dataset to use the system then proceeds to the synthetic augmentation selection. If the user just wants to validate, the default all-condition stack with the best performing model is always selected. Otherwise, if the user desires to configure the synthetic generation the system then prompts the user to select the desired adverse weather conditions from the catalogue (registered and enabled by the Argus team). For each adverse weather condition the system prompts a list of all generative models with its related KPIs for selection. Additionally, the aggregate of all adverse weather conditions is also listed. Selected weather stacks and model configurations can be saved to reuse in the future. 

Upon confirmation, the dataset selected is thus synthetically augmented with the selected adverse weather effects. FDI and IS scores are obtained and presented to the user to evaluate the qualitatively the results from the GAN stack. If the goal of the user was to augment it for extending its training set, then the user can download those images. Alternatively, if the user wanted the synthetic test dataset augmentation to use it for testing of a model, the user is then prompted to select the model. It can be either a proprietary model or a sample model for testing.

Subsets of the testing dataset can be listed to allow detection of useful edge cases that are noteworthy, and allow comparing them across multiple models to quickly identify if a new version solves previously complex scenarios where the models struggled. Datasets should also be analyzed to ensure there is not oversampling of specific scenarios ensuring that the dataset is representative of the real world.

The model is then tested on the synthetically augmented dataset (including the real images) and the model results are visually presented. Insights are provided into the dataset. The model can also be compared with previous models to evaluate its performance over time, and view insights into specific cases that have improved. 
