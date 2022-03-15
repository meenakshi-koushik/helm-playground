# Katas to Learn helm

Learn helm by completing challenges!

Below is a graded list of problem statements with some hints to try out on a k8s cluster.

1. Identify version of helm installed on your system
2. List repositories configured on your helm installation.
3. Add the bitnami charts repository
4. Install nginx helm chart from the bitnami repo. Keep in mind the namespace to install to.
5. List all helm "releases" in your cluster. Verify nginx is present.
6. Identify and connect to nginx service from your browser.
7. Install another instance of nginx using a different version of the chart
8. List and verify both instances are active and both services can be reached.
9. Clean-up (remove) both the installations. Leave the namespace untouched.
10. 