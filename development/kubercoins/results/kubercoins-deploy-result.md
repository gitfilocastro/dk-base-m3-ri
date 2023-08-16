Nombre de la asignación
Cesareo Flores
Damaso Fernandez
Roberto Torres
Filogonio Castro
Victor Saucedo
Jorge Rolando Rodriguez

Nombre
deploying-sample-application

Actividad

kubectl get nodes
git clone https://github.com/jpetazzo/container.training
kubectl apply -f ~/container.training/k8s/dockercoins.yaml
kubectl logs deploy/worker
kubectl logs deploy/hasher
kubectl get svc webui
curl 10.101.12.24
kubectl get svc webui -o wide
kubectl patch svc webui -p '{"spec": {"externalIPs": "52.35.156.42"}}'


Recurso externo

Se agrego el puerto 31130 a las reglas de seguridad para que fuera accesible de forma externa

Anexar artifactos al directorio de respuesta

http://52.35.156.42:31103/index.html
