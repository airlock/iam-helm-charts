# Airlock IAM Helm Charts

*Airlock IAM is a comprehensive authentication and identity management solution for web applications and services that features a high degree of customization.*

<picture>
<img alt="Airlock IAM" src="https://raw.githubusercontent.com/airlock/iam-helm-charts/main/media/Airlock_IAM_Icon.svg" align="left" width="120">
</picture>

This repository contains a demo version of Helm charts to set up a simple instance of Airlock IAM. These Helm charts are intended for demo purposes only and to be used in conjunction with the production-grade [Airlock Microgateway Helm Charts](https://github.com/airlock/iam-microgateway-template-charts/tree/main). 

For more information, please refer to the READMEs in the respective IAM version directories.

## Disclaimer

The Helm Charts contained in this repository are work in progress and will be improved over time to adopt new functionality of newer versions of Airlock Microgateway.

In their current state, they serve to demonstrate how Airlock Microgateway 4.0 and above can be used to protect Airlock IAM,
and may be used as a base for your extensions.

The Helm Charts provided for Airlock IAM are only suitable for demonstration purposes.

## Documentation and Links

Documentation on Airlock IAM may be found at **[docs.airlock.com](https://docs.airlock.com/iam/latest/)** or the product website at **[Airlock Identity and Access Management](https://www.airlock.com/en/secure-access-hub/components/iam)**.

For setting up Airlock Microgateway 4.0 and above, please check the following repository:

* [Airlock Microgateway on Github](https://github.com/airlock/iam-microgateway-template-charts)

# Installation Guide

The instructions below provide a short guide on how to set up Airlock IAM with Airlock Microgateway 4.X.

## Prerequisites

* Kubernetes
* Helm
* Microgateway 4.X

In addition, a valid Airlock IAM license is required to make use of its features. Once it is deployed, the license can be entered directly in the Admin UI.

### Microgateway Deployment

If you wish to run Airlock IAM with Airlock Microgateway, you will need to deploy Airlock Microgateway first.

For further instructions, please refer to the quick start guide found here: [https://github.com/airlock/microgateway](https://github.com/airlock/microgateway/blob/main/README.md#quick-start-guide)

### IAM Deployment

To install the Airlock IAM chart, please navigate to the respective version folder inside `./charts`

You can install the chart on your Kubernetes cluster using the following Helm command:

```
helm install airlock-iam --set image.repository="<repository>" --set image.tag="<version-tag>" 
```

This will deploy the application "airlock-iam", pulling the image from the given repository.

If you wish to run Airlock IAM without Microgateway, you may specify the following parameter:

```
helm install airlock-iam --set microgateway.enabled=false --set image.repository="<repository>" --set image.tag="<version-tag>" 
```

Inside "values.yaml" you will find additional configuration options.

## Support

If you have a paid license, please follow the [premium support process](https://techzone.ergon.ch/support-process).

# License
The helm charts in this repository are released under the MIT License.

For the software contained in the Airlock IAM image, please view the [license terms on the official website](https://www.airlock.com/en/airlock-license).
* Note that decompiling or reverse engineering of the software in the image is not permitted.

Airlock<sup>&#174;</sup> is a security innovation by [ergon](https://www.ergon.ch/en)

<!-- Airlock SAH Logo (different image for light/dark mode) -->
<a href="https://www.airlock.com/en/secure-access-hub/">
<picture>
    <source media="(prefers-color-scheme: dark)"
        srcset="https://raw.githubusercontent.com/airlock/iam-helm-charts/main/media/Airlock_Logo_Negative.png">
    <source media="(prefers-color-scheme: light)"
        srcset="https://raw.githubusercontent.com/airlock/iam-helm-charts/main/media/Airlock_Logo.png">
    <img alt="Airlock Secure Access Hub" src="https://raw.githubusercontent.com/airlock/iam-helm-charts/main/media/Airlock_Logo.png" width="150">
</picture>
</a>
