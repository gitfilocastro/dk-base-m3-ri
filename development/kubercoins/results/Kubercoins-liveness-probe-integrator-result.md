# Nombre de la asignación

Participantes
- Nombre
Jorge Rolando
Damaso Fernandez
Cesareo
Roberto JOb
Filogonio Castro
Actividades
- Actividad

# p. 399 - Creating a new namespace

# Create the yellow namespace
kubectl create namespace yellow

# Switch to that namespace
kns yellow

# p. 396 - Retrieving DockerCoins manifests
```
cd ~
git clone https://github.com/jpetazzo/kubercoins
```
# Get to kubercoins/
cd kubercoins

# p. 398 - Adding the liveness probe
# Add the liveness probe to rng
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
ab -c 10 -n 1000 http://<ClusterIP>/1

ab -c 10 -n 1000 http://<ClusterIP>/1
#TODO: Test with higher values of -c and assess the results
# -c sets the number of concurrent requests
# Keep the trailing /1 in the url to generate actual traffic

# OPTIONAL: Clean up
# Peform these steps if asked by your facilitator
cd ~/kubercoins
kubectl delete -f .
kns default
kubectl delete namespace yellow


Comandos
- Comandos

Recursos externos
- Recurso externo

Artifactos
- Anexar artifactos al directorio de respuesta
