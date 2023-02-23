# Core Layout

There are a number of components in the core repository. These include:

* Main Pixlise API
* Quant Job Updater Lambda Function
* Dataset Tile Updater Lambda Function
* Data Import Lambda Function
* Integration Test CLI Application
* Import Integration Test CLI Application

The codebase itself is written in Golang and resides in various packages.

core - contains the majority of shared code inside this folder are a number of packages that control the operation of the majority of the platform.

api - contains the code for controlling the API, including config, endpoints, routes, permissions, middleware and so on.

data-import - the data import lambda controls the data coming into the platform executing the conversion from raw data into the pixlise file format.

internal - inside the internal folder are the packages that make up the majority of the platform. cmdline-tools includes a number of tools used in production and development. lambdas contains the lambda functions mainly used for data format processing and quant job processing. pixlise-api contains the main hooks for the API used to control the UI.

There is also a link to the data-formats repository as a submodule which is used during the build of the platform.

