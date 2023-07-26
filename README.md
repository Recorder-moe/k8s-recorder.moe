# k8s-recorder.moe

## Usage

To use the charts, you must have [Helm](https://helm.sh) installed. Refer to Helm's [documentation](https://helm.sh/docs) for installation instructions.

Once Helm is set up correctly, add the repository by running:

```bash
helm repo add recordermoe https://recorder-moe.github.io/k8s-recorder.moe
```

If you've already added this repository before, run `helm repo update` to get the latest package versions. You can then search for available charts with `helm search repo recordermoe`.

Before installing a chart, create a `values.yaml` file and override default settings according to your needs. Download the [default values.yaml](/recordermoe/values.yaml), and edit it as required:

> **Warning**\
> The `values.yaml` must be prepared before installing the chart.\
> The default values.yaml is a template and **cannot be used as is!**

```bash
curl https://raw.githubusercontent.com/Recorder-moe/k8s-recorder.moe/master/recordermoe/values.yaml > values.yaml
```

After preparing the `values.yaml`, install the chart using:

```bash
helm install my-recorder recordermoe/recordermoe --values values.yaml
```

Check if my-recorder is running by executing:

```bash
kubectl get all -l app.kubernetes.io/instance=my-recorder
```

To uninstall the chart, run:

```bash
helm delete my-recorder
```
