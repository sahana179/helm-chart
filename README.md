<a name="FASTAPI helm-chart"></a>
# FASTAPI Helm Chart
This is the Helm chart for the FASTAPI application, which can be found below:

* https://github.com/sahana179/FastAPI

We have environment specific values for their deployment here in a `values-{env}.yaml`, for each of the following `{env}`:
* dev
* qa


<a name="table-of-contents"></a>
## Table of Contents
<!--ts-->
* [Usage](#usage)
   * [Installing the Chart](#installing-the-chart)
   * [Uninstalling the Chart](#uninstalling-the-chart)
<!--te-->

<a name="usage"></a>
## Usage

<a name="installing-the-chart"></a>
### Installing the Chart
Installing the chart (or upgrading) can be done by using the example below. You must replace `<Target_Image_Tag>` with the correct values of the Image to be deployed in the target environment.
```
helm upgrade \
   --install fastapi \
   fastapi \
   --namespace <target namespace> \
   --values ./fastapi/values-<target environment>.yaml \
   --set image.tag= <Target_Image_Tag>
```

An example of deploying the fastapi to the qa environment would be:
```
helm upgrade \
   --install fastapi \
   fastapi \
   --namespace fa-qa \
   --values ./fastapi/values-qa.yaml \
   --set image.tag= 43
```

<a name="uninstalling-the-chart"></a>
### Uninstalling the Chart
```
helm delete fastapi -n <target-namespace>
```
