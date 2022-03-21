# Movella Assessment

### Components Used:
- docker
- helm
- GKE
- Docker Hub Registry

### Step to install the app.

1. Install minikube and create a local cluster by following the below link:
  
   ``` https://minikube.sigs.k8s.io/docs/start/ ```

2. Install Helm by following the below link:

   ``` https://helm.sh/docs/intro/install/ ```

3. Make sure Cluster and Helm util is ready.
   
4. Create a docker serect object in K8S to pull private images.
    
    ```kubectl create secret docker-registry regcred --docker-server=<your-registry-server> --docker-username=<your-name> --docker-password=<your-pword> --docker-email=<your-email>```
    
    where:

         <your-registry-server> is your Private Docker Registry FQDN. Use https://index.docker.io/v1/ for DockerHub.
         <your-name> is your Docker username.
         <your-pword> is your Docker password.
         <your-email> is your Docker email.


5. Modify the helm values file and add the docker image pull secret name.

6. Install the helm chart. Using 

    ``` helm install absnginx ./ -n default```