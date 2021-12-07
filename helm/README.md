Various notes on deploying Charts on my cluster

## MetalLB

**Enable strict ARP mode when using kube-proxy in IPVS mode**

  To enable strict ARP mode, simply edit the `kube-proxy` ConfigMap :

  ```YAML
  $ kubectl edit configmap -n kube-system kube-proxy
  
  apiVersion: kubeproxy.config.k8s.io/v1alpha1
  kind: KubeProxyConfiguration
  mode: "ipvs"
  ipvs:
    strictARP: true
  ```

## Charts references

- **MetalLB** : https://github.com/metallb/metallb/tree/main/charts/metallb
- **OpenEBS** : https://github.com/openebs/charts
- **Traefik** : https://github.com/traefik/traefik-helm-chart
- **Velero** : https://vmware-tanzu.github.io/helm-charts/ 