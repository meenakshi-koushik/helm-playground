# Katas to Learn helm

Learn helm by completing challenges!

Below is a graded list of problem statements with some hints to try out on a k8s cluster. Refer [Resources](resources.md) for some handy links with information helpful for solving these challenges.

### Ensure access to cluster and helm
1. Identify version of `kubectl` installed on your system.
    The binary is already installed. Use `kubectl version` to print-out the version.
2. Identify version of `helm` installed on your system
    The binary is already installed. Use `helm version` to print-out the version.
3. Are there any helm "releases" already present in the cluster ? (Hint: use `helm list`)
4. What namespace are you using for your deployments ? Are there any pods running in this namespace ?
5. Is Lens able to connect to the cluster and display resources in the selected namespace ?

### Install and remove releases

1. List repositories configured on your helm installation.
2. Add the bitnami charts repository (https://charts.bitnami.com/bitnami)
3. Install nginx helm chart from the bitnami repo. Keep in mind the namespace to install to.
4. List all helm "releases" in your cluster. Verify nginx is present.
5. Identify and connect to nginx service from your browser.
6. Install another instance of nginx using version 9.6.0 of the chart
7. List and verify both instances are active and both services can be reached.
8. Clean-up (remove) both the installations. Leave the namespace untouched.

### Upgrade and rollback
1. What versions of nginx chart are avaiable in the bitnami repo ?
2. install the version 9.6.0 of nginx chart. What is the container image version ?
3. update the release to the latest version
4. list the revisions of the nginx release
5. Use helm to rollback the changes
6. Edit the container image version using kubectl
7. Use helm to rollback the changes
8. clean-up the nginx installation

Bonus: were there any resources that didn't get destroyed/ recreated during the rollback/ upgrade ?

### Install from local path and additional helm CLI commands
1. Download (Pull) and extract version 9.9.3 of nginx chart from bitnami charts repository
2. Customize the chart to always pull the nginx image.
3. Check the chart for errors and install this version
4. install the [gitea](https://artifacthub.io/packages/helm/gitea/gitea) helm chart.
5. what is the application version packaged in the gitea chart version 2.1.4 ?
6. How many services of what type does the gitea helm chart create ? How many secrets ?
7. Review the helm chart located in the `charts/angular-starter-learning` subfolder.
   This chart is the output from an earlier learning session. More details [here](https://github.com/meenakshi-koushik/angular-starter-learning)
8. check the helm chart for errors (hint: see [helm lint](https://docs.helm.sh/docs/helm/helm_lint/))
9. install the chart on your cluster and try to access the application
10. remove the nginx and gitea installations

### Customizing behaviour through values.yaml
1. install nginx chart with a replica count for the deployment set to 3 and debug mode enabled
2. Customize the chart to serve a static HTML web-page that prints "Hello from Team Learning Session!". 
3. Is there a way to re-install with previous customizations carried over from the previous release ?
4. setup nginx to serve static content from one of the following:

  *  https://github.com/cloudacademy/static-website-example
  *  https://github.com/mdn/beginner-html-site-styled
5. explore other possible customization options that are interesting for you.
6. Find out all the customizations set on your current installation of nginx

### Dependencies and sub-charts

Your goal is to setup a cluster with development infrastructure for a new project. Try to package the solution as a single helm-chart and use off-the-shelf components where applicable.

1. Create a chart that installs the following

    1. gitea with mariadb as backend database, for source control. (Hint: what backend customization options does gitea come with ?)
       Make sure the application is accessible via a service of type LoadBalancer.
    2. jenkins for CI
    3. ghost for project blog
    4. nginx for landing page. 
    5. configure nginx to serve a static page, 
    6. optionally configure nginx landing page to connect to gitea, jenkins and ghost
### User Permisions (Role-based access control)

TBD
