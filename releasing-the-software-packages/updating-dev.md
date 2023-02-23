---
description: How to update the development environment
---

# Updating Dev

To update the development environment follow these instructions:



Commit your code to either dev, or a feature branch. As we don't currently have review environments then we have to pivot dev to use either a feature build or the development build as people see fit.

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 191352.png" alt=""><figcaption><p>Example Docker Repo</p></figcaption></figure>

Pick out your image tag from either the Core or the UI repository:

* [https://github.com/pixlise/pixlise-ui/pkgs/container/pixlise-ui](https://github.com/pixlise/pixlise-ui/pkgs/container/pixlise-ui)
* [https://github.com/pixlise/core/pkgs/container/core](https://github.com/pixlise/core/pkgs/container/core)

Update the fixedEnvs.json file as required with the correct docker tag: [https://gitlab.com/pixlise/infrastructure-setup/-/blob/main/cdk/config/fixedEnvs.json](https://gitlab.com/pixlise/infrastructure-setup/-/blob/main/cdk/config/fixedEnvs.json)

<figure><img src="../.gitbook/assets/Screenshot 2022-09-16 191657.png" alt=""><figcaption><p>Pipeline Trigger</p></figcaption></figure>

Then trigger the infra pipeline with the above details. STACK\_NAME dev.

Press run and CDK should deploy your new environment. If it does not a Cloudformation and Helm rollback are likely required.
