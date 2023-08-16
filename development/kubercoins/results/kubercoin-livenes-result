Nombre de la asignación
Cesareo Flores
Damaso Fernandez
Roberto Torres
Filogonio Castro
Victor Saucedo
Jorge Rolando Rodriguez

Nombre
kubercoins-liveness-probe-integrate.md

Actividad
kubercoins-liveness-probe-integrate.md

Comandos 


# Create the yellow namespace
kubectl create namespace yellow

# Switch to that namespace
kns yellow


cd ~
git clone https://github.com/jpetazzo/kubercoins
```
# Get to kubercoins/
cd kubercoins


vim rng-deployment.yaml
# Insert the following code below name: rng
```
        livenessProbe:
          httpGet:
            path: /
            port: 80
          initialDelaySeconds: 30
          periodSeconds: 5
```


# Load the YAML for all the resources of DockerCoins
kubectl apply -f .

# p. 399 - Testing the liveness probe
# Get the ClusterIP address of the rng service
kubectl get svc rng

# p. 400 - Monitoring the rng service
# [window 1] monitor cluster events
kubectl get events -w
# [window 2] monitor the response time of rng
httping <ClusterIP>
# [window 3] monitor pod status
kubectl get pods -w

# p. 401 - Generating traffic
# [window 4] Generate traffic with ab
ab -c 10 -n 1000 http://10.99.132.79/1

