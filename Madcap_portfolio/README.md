<h1>━━━━━━🛟 Projet Madcap1874 ⛵━━━━━━</h1>


![Header du site Madcap](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/header.png)


## ⛵ Présentation du Projet
Madcap1874 est un site web développé pour présenter l'histoire du bateau Madcap, promouvoir l'association, permettre l'inscription de nouveaux membres et recueillir les témoignages des visiteurs. Le site est également un espace interactif avec une météo en temps réel, des informations sur les événements à venir et des liens pour soutenir l'association.

## 🌐 Hébergement & Déploiement
Le site Madcap1874 est hébergé sur Pythonanywhere  [⛵ --------Visitez Madcap1874 --------⛵](https://madcap1874.pythonanywhere.com//)

![Déploiement Render ok](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/render_builtok.png)

🚀 Déploiement sur Render
Base de données 
PostgreSQL est utilisé sur Render.com
Ajout des variables d’environnement (DATABASE_URL)

## ⚙ Technologies Utilisées
- **Framework Backend** : Django (Python)
- **Base de données** : Postgre
- **Frontend** : HTML, CSS, JavaScript
- **API météo** : Intégration de la carte Windy pour la météo en direct
- **Système de gestion des avis** : Stockage et validation des avis avant affichage
- **Traduction du site** : Flask-Babel pour la gestion des langues (FR & EN)

![Carte live Windy](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/windy.png)

## 🌐 Structure du Site

## ⚙ **Technologies utilisées**
| Technologie | Description |
|------------|------------|
| **Backend** | Django (Python) |
| **Base de données** | PostgreSQL & SQLite |
| **Frontend** | HTML, CSS, JavaScript |
| **API météo** | Intégration de la carte **Windy** interactive en live avec mode plein écran |
| **Traduction** | Django i18n (FR 🇫🇷 & EN 🇬🇧) |
| **Hébergement** | Render (Base de données & serveur web) |


![Architecture web](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/Diagramme_web.png)


### ⚡ Démarrer le serveur Django
```bash
python3 manage.py runserver
    Accéder au site sur http://127.0.0.1:8000/ 🚀
```

### ⛵ Page d'Accueil (`index.html`)
- Présentation du Madcap avec une vidéo.
- Deux liens cliquables :
  - **Adhérer à l'association** via HelloAsso.
  - **Page de contact** pour plus d'informations.
- Choix de la langue (français/anglais).

### 📝 Histoire du Madcap (`histoire.html`)
- Résumé de l'histoire du bateau de 1874 à aujourd'hui.
- Illustrations et descriptions des différentes époques.

## 🏛️ À propos de l'Association (association.html)
📜 Présentation de l’**histoire** et des **valeurs** de l’association Madcap1874  
👥 Informations sur les **membres fondateurs** et les **bénévoles**  
💡 Objectifs et **missions** de l’association  
📌 **Comment adhérer** à l’association et devenir membre  
🔗 [💖 Soutenir Madcap sur HelloAsso](https://www.helloasso.com/associations/madcap-1874)  

### 🎣 Page Événements (`evenements.html`)
- Calendrier des événements auxquels Madcap participera en 2025.

### 👨‍🌾 Soutenir le Projet (`don.html`)
- Explication des différents moyens de soutenir Madcap.
- Lien cliquable vers HelloAsso pour les dons.


### 📝 **Livre d’or & Avis** (`livre_dor.html`)
- 🖊️ **Laisser un avis** avec une note sur 5 étoiles ⭐⭐⭐⭐⭐
- 📃 **Afficher les avis** du plus récent au plus ancien
- 🛠️ **Validation manuelle** avant publication
- 📸 **Ajout jusqu'à quatre photos** possible

### 📞 Page Contact (`contact.html`)
- Formulaire de contact.
- Numéro de téléphone et email de l'association.
- **Carte interactive** situant Madcap à Canet-en-Roussillon.

### 🏠 Interface Administrateur
- Gestion des membres de l'association.
- Validation des avis avant publication.
- Interface de recherche dynamique pour les membres.

![ Liste membres du site Madcap](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/membres.png)

### 🦶 Footer du site

Ajout d'un footer amélioré avec des liens vers les réseaux sociaux et des informations de contact.

Affichage dynamique des mentions légales et des crédits du site.

![Footer du site Madcap](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/footer.png)

### 📄 Téléchargement des documents

Possibilité de télécharger le bulletin d'inscription 2025 et le règlement intérieur directement en local sur le PC.

## 🛠 **Installation & Déploiement**
### 📦 **1. Cloner le projet**

    git clone https://github.com/utilisateur/Madcap1874.git
    cd Madcap1874

## 2. Créer & activer un environnement virtuel

    python3 -m venv venv  # Création de l’environnement virtuel
    source venv/bin/activate  # Activation (Linux/macOS)
    venv\Scripts\activate  # Activation (Windows)

    
## 3. 📊 Gestion des Bases de Données
### 👨‍🌾 Table des Membres (`madcap_app_member`)

![Diagramme_database.drawio](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/Diagramme_database.drawio.png)

### 🔒 Créer un super-utilisateur
```bash
python3 manage.py createsuperuser
```

### 📈 Gestion de la Base de Données Postgre
```bash
python3 manage.py dbshell
.tables
SELECT * FROM madcap_app_member;
SELECT * FROM madcap_app_avis;
```

![Migrations deux tables](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/migrations2tables.jpg)

Stocke les informations des membres de l'association :
```sql
CREATE TABLE madcap_app_member (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    address TEXT NOT NULL,
    phone TEXT UNIQUE NOT NULL,
    date_entree DATE
);
```
**Exemples de requêtes SQL :**
```sql
INSERT INTO madcap_app_member (name, address, phone, date_entree) VALUES ('Xavier Dupont', '123 Rue de Paris', '0123456789', '2025');
SELECT * FROM madcap_app_member;
DELETE FROM madcap_app_member WHERE id = 3;
UPDATE madcap_app_member SET phone = '0987654321' WHERE id = 1;
```

### 💬 Table des Avis (`madcap_app_avis`)
Stocke les avis des visiteurs sur le site.
```sql
CREATE TABLE madcap_app_avis (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nom TEXT NOT NULL,
    email TEXT NOT NULL,
    telephone TEXT NOT NULL,
    commentaire TEXT NOT NULL,
    note INTEGER NOT NULL CHECK(note BETWEEN 1 AND 5),
    date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    valide BOOLEAN DEFAULT FALSE
);
```
![Envois avis ok ](https://raw.githubusercontent.com/Xa-C24/Madcap/main/static/images/image_docs/Envoi_ok.png)


**Exemples de requêtes SQL :**
```sql
INSERT INTO madcap_app_avis (nom, email, telephone, commentaire, note, valide) VALUES ('Jean Dupont', 'jean.dupont@example.com', '0601020304', 'Super expérience !', 5, 0);
SELECT * FROM madcap_app_avis WHERE valide = 1;
UPDATE madcap_app_avis SET valide = 1 WHERE id = 1;
```



## 🛠 Commandes Utiles
### ⚙ Installation des dépendances
    pip install -r requirements.txt
```bash
pip install flask flask-babel django
```



## 🎨 Outils de Développement
- **Live Server** pour recharger les pages automatiquement :
  ```bash
  npm install -g browser-sync
  browser-sync start --proxy "127.0.0.1:8000" --files "templates/**/*.html, static/**/*.css, static/**/*.js"
  ```
- **Extension VS Code** : Prettier pour le formatage du code.

## 4. Configurer les variables d’environnement
    DJANGO_SECRET_KEY=super_secret_key
    DEBUG=True
    ALLOWED_HOSTS=*
    DATABASE_URL=postgres://user:password@host:port/dbname


---

## 5. 🌍 Version Multilingue (FR & EN)  
Le site Madcap1874 est disponible en français et en anglais.
La traduction est gérée avec Django et gettext, permettant aux utilisateurs de naviguer dans la langue de leur choix.

### ⚙ Installation des bibliothèques pour la traduction

    pip install babel django-babel

### 📜 Comment ça fonctionne ?  
Django utilise le middleware de traduction (LocaleMiddleware).  

Les fichiers .po contiennent les traductions et sont compilés en .mo pour être utilisés par le site.  

Les balises {% trans %} et {% blocktrans %} permettent d’afficher du texte traduit dans les templates.  

### 🔄 Générer et mettre à jour les traductions
1. Extraire les chaînes de caractères à traduire:  
      django-admin makemessages -l en

2. Modifier les fichiers de traduction (.po) dans 
      locale/en/LC_MESSAGES/django.po. 

3. Compiler les fichiers de traduction;
      django-admin compilemessages

Un sélecteur de langue est disponible sur le site permettant de basculer entre les flags FR <img src="https://github.com/Xa-C24/Madcap/blob/main/static/images/Flag_France.jpg?raw=true" width="25"/> et UK <img src="https://github.com/Xa-C24/Madcap/blob/main/static/images/Flag_Uk.jpg?raw=true" width="25"/>.


## 6. 📜 Commandes pour exécuter les tests

    # Tester avec Django
    python manage.py test madcap_app.tests


![Unitest_urls_ok](https://github.com/Xa-C24/Madcap/blob/main/static/images/image_docs/unitest_urls.jpg)


    
###  Outils de développement
    pip install pytest pytest-django dj-database-url


# Tester avec Pytest
pytest madcap_app/tests/
## 🌟 Conclusion
Le projet Madcap1874 vise à promouvoir et préserver l'histoire du bateau Madcap tout en facilitant l'implication des membres et des visiteurs. Le site est conçu pour être interactif, informatif et accessible.

💡 Prochaine étape :

Améliorer encore le design et l'expérience utilisateur.

Développement d'une nouvelle version de Madcap en utilisant Django, React, Tailwind CSS et GSAP pour une interface plus moderne et dynamique. 🚀

