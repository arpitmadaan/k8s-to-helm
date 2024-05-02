## Packaging Kubernetes manifest files into helm chart
### Here's the process to package the Helm chart:

#### Navigate to the Chart Directory: Change your current directory to the directory containing your Chart.yaml file and the chart's directory structure.
#### Package the Chart: Use the helm package command to package your chart. This command creates a versioned chart package (.tgz file) based on the contents of the chart directory.

helm package <chart-directory>
#### Replace <chart-directory> with the name of your chart directory. For example, if your chart directory is named application, you would run:

helm package application
#### This will create a <chart-name>-<chart-version>.tgz file in your current directory.
#### For example, if your chart name is application and the version specified in Chart.yaml is 1.0.0, the generated file will be named application-1.0.0.tgz.
#### After packaging, you can distribute this .tgz file for installation on Kubernetes clusters.
#### Additionally, if you're hosting your own chart repository, you can use the helm repo index command to generate or update the index.yaml file, which contains metadata about the charts in your repository. This is necessary for Helm clients to discover and install charts from your repository.
####Here's how to generate or update the index.yaml file:

helm repo index <repository-directory>
#### Replace <repository-directory> with the directory containing your packaged charts. This command creates or updates the index.yaml file in that directory, which includes information about all the packaged charts.
## Applying helm charts
### To apply a Helm chart with a values file, you can use the following command:

helm install <release-name> <chart-name> -n <namespace> -f <values-file>
#### <release-name> is the name you give to this release of the chart.
#### <chart-name> is the name of the Helm chart.
#### <namespace> is the Kubernetes namespace where you want to install the chart.
#### <values-file> is the path to the values file you want to use. If not specified, Helm uses the default values.yaml file.

### For example, if you have a Helm chart named application and a values file named my-values.yaml, and you want to install it in the default namespace with the release name my-release, you would use the following command:

helm install my-release application -n default -f my-values.yaml
####This command installs the Helm chart application with the release name my-release in the default namespace, using the values defined in my-values.yaml.






