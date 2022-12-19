# Costs

The main operating costs of the proposed Argus system are the following:

- Developer / Engineer and other HR salaries
- Data storage costs for datasets (S3, GCS, Azure Blob Storage, ClearML Hyper-Datasets)
- Infrastructure DevOps costs (Self-hosted servers, Cloud-based servers)
- GPU training costs (GPUs, AWS, GCP, Azure, ClearML)
- Experiment Analytics and Logging costs ( Self-hosted, Neptune, Tensorboard, Weights and Biases, ClearML Experiment)
- Metadata storage costs ( Self-hosted, Neptune, MLFlow)
- Model Deployment costs ( Self-hosted, Seldon, ClearML Deploy)
- Model Registry costs ( Self-hosted, Neptune, MLFlow, ClearML)

Most of these costs are highly variable, and tend to be more expensive when the system is in production and under client load. The costs of the system are highly dependent on the number of models that are being trained, and the number of datasets that are being used. Most of these systems are billed based on use, which allows flexibility when scaling up and down the system. A correct budgeting and optimization of usage costs can ensure the optimal usage of each component to make the system as cost-effective as possible.

These costs tend to be highly beneficial as any system that empowers internal developers to be more efficient has a direct impact on the bottom line of the company by improving efficiency and availability. For example, a MLOps system that allows for the training of models to be automated and streamlined can free up the time of the data scientists to work on other tasks, and can also allow for the training of more models, which in turn can increase the productivity of the company. Similarly, analyzing and visualizing efficiently the results of generative models can increase the turnaround time of the development cycle, and thus allow faster releases to satisfy the needs of the clients.