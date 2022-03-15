# Katas to Learn helm

Learn helm by completing challenges!

Below is a graded list of problem statements with some hints to try out on a k8s cluster.

### Install and remove releases
1. Identify version of helm installed on your system
2. List repositories configured on your helm installation.
3. Add the bitnami charts repository (https://charts.bitnami.com/bitnami)
4. Install nginx helm chart from the bitnami repo. Keep in mind the namespace to install to.
5. List all helm "releases" in your cluster. Verify nginx is present.
6. Identify and connect to nginx service from your browser.
7. Install another instance of nginx using version 9.6.0 of the chart
8. List and verify both instances are active and both services can be reached.
9. Clean-up (remove) both the installations. Leave the namespace untouched.

### Upgrade and rollback
1. What versions of nginx chart are avaiable in the bitnami repo ?
2. install the version 9.6.0 of nginx chart. What is the container  image version ?
3. Edit the container image version using kubectl
4. Use helm to rollback the changes
5. update the release to the latest version
6. list the revisions of the nginx release

### Customizing behaviour through values.yaml

### Dependencies and sub-charts
1. Create a chart that installs 

### User Permisions (Role-based access control)
