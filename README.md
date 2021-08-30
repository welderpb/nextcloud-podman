# Run nextcloud using podman or minikube
Manifest Deployments to create nextcloud pod

### Podman
- Install podman for your OS
- cd in cloned repository
- ```sudo mkdir -p /mnt/nextcloud```
- ```sudo mount -o bind mount /mnt/nextcloud```
- ```podman play kube nextcloud-podman.yaml```
- check if nextloud up and running: http://127.0.0.1:8081/

### Minikube(podman driver)
- Install minikube for your OS
- cd in cloned repository
- ```minikube start --driver=podman --mount --mount-string="${PWD}/mount:/mnt/nextcloud"```
- ```kubectl apply -f nextcloud-podman.yaml```
- check if nextcloud up and running:
- ```kubectl expose pod nextcloud --type=NodePort```
- ```minikube service nextcloud --url```
