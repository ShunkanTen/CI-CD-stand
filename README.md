
This **gitlab-runner** executes **CI/CD** jobs in a **cluster-kubernetes** for projects hosted on **GitLab**. We have utilized the **Helm Chart** package manager to simplify the management and deployment of applications in **Kubernetes** for this purpose.

### Prerequisites for setting up GitLab Runner:

1. Your GitLab server’s API is reachable from the cluster.
2. Kubernetes 1.4+ with Beta APIs enabled.
3. The kubectl CLI installed locally and authenticated for the cluster.
4. The [Helm client](https://helm.sh/docs/intro/) installed locally on your machine.



### Installing GitLab Runner using the Helm Chart в K8s:

* Initialize Helm and add the GitLab Helm repository.
* Create a new GitLab Runner in your project.
* Create a new Chart where you will write your [values.yml](https://docs.gitlab.com/runner/install/kubernetes.html#configuring-gitlab-runner-using-the-helm-chart) tailored to your needs.
* Use the following command to install the runner in the desired namespace:
```
helm install --namespace <NAMESPACE> gitlab-runner -f <CONFIG_VALUES_FILE> gitlab/gitlab-runner
```
   Where:

   * `<NAMESPACE>` is the Kubernetes namespace where you want to install GitLab Runner.
   * `<CONFIG_VALUES_FILE>` is the path to the values file containing your custom configuration.
