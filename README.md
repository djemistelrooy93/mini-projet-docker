# Mini Projet Docker

## Introduction
Ce projet vise à démontrer l'utilisation de Docker pour créer et exécuter des applications dans des conteneurs. Ce README fournit un aperçu des étapes suivies pour configurer et exécuter le projet, ainsi que des informations sur les problèmes rencontrés et leur résolution.

## Étapes de développement

1. **Création du repository GitHub :** J'ai créé un repository sur mon GitHub personnel pour travailler et documenter l'ensemble du projet : https://github.com/djemistelrooy93/mini-projet-docker/

2. **Récupération du code source :** Dans un premier temps, j'ai récupéré le code source nécessaire au projet : https://github.com/diranetafen/student-list/

3. **Rédaction du Dockerfile :** Suite à la lecture de la documentation et des requirements, j'ai rédigé le Dockerfile adéquat en rajoutant les informations nécessaires au bon build et au bon lancement de l'image et du conteneur. Cependant, j'ai rencontré des premières difficultés lors du build de l’image suite à l’installation des requirements.txt : certaines librairies devaient être rajoutées lors du build de mon image, notamment `python-dev`, `python3-dev`, `libsasl2-dev`, `python-dev`, `libldap2-dev`, `libssl-dev`.
![Error1](screenshots/2_error1.PNG)
![Dockerfile](screenshots/1_Dockerfile.PNG)

4. **Lancement du conteneur Docker :** J'ai lancé mon conteneur Docker avec la commande suivante : docker run -d -p 5000:5000 -v ./student_age.json:/data/student_age.json --name api simple_api:v1
![dockerrun](screenshots/3_dockerrun.PNG)

5. **Vérification du volume monté :** On peut se connecter au conteneur et vérifier que le volume data a bien été monté avec le bon fichier dedans.
![dockerexec](screenshots/4_dockerexec.PNG)

6. **Test final de l'API :** Pour vérifier le bon fonctionnement de l'API, j'ai utilisé la commande suivante : curl -u toto:python -X GET http://172.17.0.2:5000/pozos/api/v1.0/get_student_ages
![curl1](screenshots/5_curl.PNG)

On peut également tenter d’y accéder via notre navigateur ; une authentification est requise. Une fois les bons credentials indiqués, on obtient bien le contenu du fichier JSON.
![browser1](screenshots/6_browser1.PNG)
![browser2](screenshots/7_browser2.PNG)


7. **Rédaction du docker-compose.yml :** Maintenant, je vais rédiger le docker-compose.yml pour faciliter la gestion des conteneurs.

## Remarque
Assurez-vous d'avoir Docker installé sur votre système avant de suivre ces étapes.

## Licence
Ce projet est sous licence [MIT](lien_vers_licence).
