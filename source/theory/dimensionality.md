# Dimensionality explosion

In the context of machine learning, dimensionality explosion, or commonly the curse of dimensionality, refers to the phenomenon of increasing the number of dimensions (or features) in a dataset to such a large extent that it becomes difficult or impossible to effectively analyze or process the data. This can occur when the number of dimensions in a dataset is much larger than the number of samples, which can lead to problems such as overfitting, poor generalization, and increased computational complexity.

To address dimensionality explosion, it may be necessary to use techniques such as feature selection, dimensionality reduction, or regularization in order to reduce the number of dimensions in the dataset and improve the performance and scalability of ML models.

## Implications

Within the scope of Argus, the dimensionality explosion arises from two areas:

- The increasing combination of possible adverse weather scenarios, and their relatively sparse frequency in the real world that significantly reduces the availability of real-world data(which typically leads to class imbalance and complexities in the model training). This makes it so that the higher-dimensional space of weather-combinations is sparse and thus makes training of generator models that can map this domain shift more complex (data needs to be taken of these low-frequency situations).

- The incredibly expansive operational space of an ADAS function(practically infinite as driving in the real world is a N-dimensional feature space in practically infinite scenarios). An advanced (L4/L5) ADAS ML model in production can potentially be expected to be in use under most of these scenarios (granted, the scenarios are clustered within this very sparse space and as such can be easily evaluated). As a validator of ADAS models Argus needs to be able to evaluate these scenarios up to a certain degree to satisfy some statistical certainty of a sufficiently well-performing model under diverse conditions. This is a general challenge of the field that is present in any ADAS solution for practical matters.

## Solutions

There is not a silver bullet to solve these issues (particularly the second, if there was, autonomous vehicles would already be operating in all cities, rather than in a few selected ones). This then needs to be tackled by alternate methods that are smaller in scope. 

For the first scenario it is then perhaps possible that the frequency within the dataset matches the expected frequency in the real world (i.e. matching the probability distributions), and a weighted metric of evaluation is then used for evaluation. The generator can then try and compensate with a perhaps limited dataset that works well with the weighted metric, and the . Additionally, statistical certainty can thus guide to an adequate number of scenarios for the generator dataset.

An interesting avenue of how this is solved is in the way nature and us humans by proxy solve it, by quickly learning from single experiences from a shared universal model and efficiently extrapolating it to unseen scenarios (i.e. I slip on a frozen floor and then know that I must be careful the first time I drive on snow).