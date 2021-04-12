# prometheus-operator-with-podmonitor
CustomResourceDefinitions

A core feature of the Prometheus Operator is to monitor the Kubernetes API server for changes to specific objects and ensure that the current Prometheus deployments match these objects. The Operator acts on the following custom resource definitions (CRDs):

Prometheus, which defines a desired Prometheus deployment.

Alertmanager, which defines a desired Alertmanager deployment.

ThanosRuler, which defines a desired Thanos Ruler deployment.

ServiceMonitor, which declaratively specifies how groups of Kubernetes services should be monitored. The Operator automatically generates Prometheus scrape configuration based on the current state of the objects in the API server.

PodMonitor, which declaratively specifies how group of pods should be monitored. The Operator automatically generates Prometheus scrape configuration based on the current state of the objects in the API server.

Probe, which declaratively specifies how groups of ingresses or static targets should be monitored. The Operator automatically generates Prometheus scrape configuration based on the definition.

PrometheusRule, which defines a desired set of Prometheus alerting and/or recording rules. The Operator generates a rule file, which can be used by Prometheus instances.

AlertmanagerConfig, which declaratively specifies subsections of the Alertmanager configuration, allowing routing of alerts to custom receivers, and setting inhibit rules.

The Prometheus operator automatically detects changes in the Kubernetes API server to any of the above objects, and ensures that matching deployments and configurations are kept in sync.

To learn more about the CRDs introduced by the Prometheus Operator have a look at the design doc.

To automate validation of your CRD configuration files see about linting.
