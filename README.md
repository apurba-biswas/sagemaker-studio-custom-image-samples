## SageMaker Studio Custom Image Samples

Modified by Apu for Trove Research

Examples run within AWS Cloud 9 environment
    - use a bigger instance (with more RAM) to create a large docker images
    - clone this repository
    - set evironment variable names/run bash script in examples

### Overview

This repository contains examples of Docker images that are valid custom images for KernelGateway Apps in SageMaker Studio. These custom images enable you to bring your own packages, files, and kernels for use with notebooks, terminals, and interactive consoles within SageMaker Studio.

### Examples

- [conda-env-kernel-image](examples/conda-env-kernel-image) - This example creates a custom Conda environment in the Docker image and demonstrates using it as a custom kernel. 
- [r-image](examples/r-image) - This example contains the `ir` kernel and a selection of R packages, along with the AWS Python SDK (boto3) and the SageMaker Python SDK which can be used from R using `reticulate`
- [tf2.3-image](examples/tf23-image) - This examples uses the official TensorFlow 2.3 image from DockerHub and demonstrates bundling custom files along with the image.

#### One-time setup

All examples have a one-time setup to create an ECR repository

```
REGION=<aws-region>
aws --region ${REGION} ecr create-repository \
    --repository-name smstudio-custom
```

### Developing Custom Images

See [DEVELOPMENT.md](DEVELOPMENT.md)

### License

This sample code is licensed under the MIT-0 License. See the LICENSE file.
