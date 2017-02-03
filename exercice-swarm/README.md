## Initialisation d'un Cluster Swarm

```
docker swarm init --advertise-addr IP_PHYSIQUE
```

## Visualisation de l'etat du noeud.

```
docker info
```

## Visualisation des noeuds du cluster.

```
docker node
```

## Ajout d'un Worker Node en récupérant la commande pour joindre depuis un Manager Node

```
docker swarm join-token worker
```

## Déploiement d'un service

```
docker service create --replicas 1 --name helloworld alpine ping docker.com
```
