## Etape 1 - Lancement du serveur Registry

```
docker run -d -p 5000:5000 --restart=always --name registry-atecna registry:2
```

## Etape 2 - Associatation de l'image avec le nouveau registry

```
docker tag daniellavoie/debian-magenta:0.0.1 localhost:5000/daniellavoie/debian-magenta:0.0.1
```

## Etape 3 - Push de la nouvelle référence

```
docker push localhost:5000/daniellavoie/debian-magenta:0.0.1
```