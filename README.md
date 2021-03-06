# TP-IGL-Front-End 

## Lancer l'application Localement : 

### Exigences 

| Exigence                                 | Version |
| ------------------------------------------- | ------- |
| [NodeJS](https://nodejs.org/en/download/) | `10.15+`  |
| [Git](https://git-scm.com/downloads) | `2.0+`  |

Exécutez les commandes suivantes pour vérifier les versions installées actuelles:

```bash
node --version
git --version
```

Puis Lancer ces commandes : 

1. Cloner le repository et monter sur le projet : :

```bash
git clone https://github.com/AbdelkhalekESI/TP-IGL-Client 
cd TP-IGL-Client
```

2. Installer les dépendances nécessaires :

```bash
npm install
```

3. Lancer l'application :

```bash
npm run serve
```

4. Accéder à l'application via : `http://127.0.0.1:8080`

5. N'oubliez pas de télécharger l'extension [Allow CORS](https://chrome.google.com/webstore/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf?hl=en) pour activer les requêtes CORS.

## Lancer l'application en utilisant Docker : 

Pour lancer l'application avec [Docker](https://www.docker.com/products/docker-desktop) installer le ,aprés éxecutez ces commandes : 

1. Cloner le repository :

```bash
git clone https://github.com/AbdelkhalekESI/TP-IGL-Client
```

2. Construire l'image Docker : 

```bash
docker build -t tp-igl/vue-app:0.1 .
```

3. Lancer le conteneur Docker : 

```bash
docker run -it -p 8080:8080 --rm tp-igl/vue-app:0.1
```

4. Accéder à l'application via : `http://127.0.0.1:8080`

## Tests Avec Selenium 

### Exigences 

| Exigence                                 | Version |
| ------------------------------------------- | ------- |
| [Python](https://www.python.org/downloads/) | `3.6+`  |
| [Pip](https://pypi.org/project/pip/) | `9.0+`  |

Avant de commancer vérifier bien que l'application est en cours d'éxecution (Front-end et Back-end) :

```bash
cd Selenium-Test
pip install selenium
python script.py
```
