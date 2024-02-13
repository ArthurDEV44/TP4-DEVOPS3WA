# Comparaison entre Docker Compose/Swarm et Kubernetes

Ci dessous je présente une comparaison entre les spécifications de Docker Compose/Swarm et celles de Kubernetes pour l'application `example-voting-app`. Les fichiers Docker Compose (`docker-compose.yml`) et Kubernetes (fichiers YAML dans le répertoire `k8s-specifications`) décrivent la configuration nécessaire pour déployer l'application dans les deux environnements.

## Structure de l'Application

L'application est composée de plusieurs services :

- **vote**
- **result**
- **worker**
- **redis**
- **db**

## Docker Compose/Swarm

Dans Docker Compose/Swarm, la configuration de chaque service inclut :

- Image Docker à utiliser.
- Ports à exposer.
- Volumes pour la persistance des données.
- Réseaux pour la communication entre services.
- Dépendances entre les services.

Le fichier `docker-compose.yml` centralise cette configuration.

## Kubernetes

Kubernetes utilise des fichiers YAML pour définir les déploiements et les services :

- **Déploiements (Deployments)** : Définissent comment créer et gérer les instances de conteneurs.
- **Services** : Exposent les applications à l'extérieur du cluster ou entre les conteneurs du cluster.

Pour chaque service Docker, il y a généralement un déploiement et un service Kubernetes correspondant.

## Équivalences Clés

1. **Services Docker**
   - Correspondent aux **Déploiements Kubernetes**.
   - Définissent les images, les ports, les volumes, etc.

2. **Volumes Docker**
   - Similaires aux **Volumes Kubernetes** pour la persistance des données.

3. **Ports Docker**
   - Équivalents aux **Services Kubernetes** pour exposer les applications.

4. **Réseaux Docker**
   - Comparables aux **réseaux au sein du cluster Kubernetes** pour la communication inter-services.

5. **Dépendances entre Services Docker**
   - Dans Kubernetes, géré via des services et des sélecteurs.

## Conclusion

La transition de Docker Compose/Swarm à Kubernetes implique une réorganisation de la configuration en déploiements et services, mais les concepts fondamentaux de services, de volumes, et de réseaux restent cohérents entre les deux systèmes.
