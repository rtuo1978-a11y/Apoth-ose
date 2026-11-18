# Apotheosis ACE — version React + API Django

Une application pour organiser le banquet d'une église : l'administrateur crée les tables et le menu, les invités s'inscrivent et choisissent leur plat. Cette version sépare l'interface (React) et l'API (Django REST Framework).

> La version finale, en Django avec des templates HTML et prête pour PythonAnywhere, est dans le dépôt [acevent](https://github.com/rtuo1978-a11y/acevent).

## Ce que fait l'application

**Pour les invités**
- Page d'accueil avec versets bibliques
- Inscription au banquet et choix de la table
- Choix du plat dans le menu, modifiable pendant 2 minutes
- Galerie d'images

**Pour l'administrateur**
- Connexion sécurisée
- Création des tables (numéro et nombre de places) et des plats
- Page « Résultats » : les tables dans l'ordre, avec les plats commandés

## Organisation

| Dossier | Contenu | Technologies |
| --- | --- | --- |
| `frontend/` | Les pages : accueil, inscription, choix du plat, galerie, connexion et tableau de bord admin | React, Tailwind CSS, Radix UI |
| `backend/` | L'API : authentification, tables, menu, invités, commandes, résultats, galerie | Django 5.2, Django REST Framework |

### Routes de l'API

| Route | Rôle |
| --- | --- |
| `auth/login`, `auth/logout`, `auth/me` | Connexion de l'administrateur |
| `tables`, `tables/create` | Lister et créer les tables |
| `menu`, `menu/create` | Lister et créer les plats |
| `guests/register`, `guests/<id>` | Inscrire un invité, voir sa fiche |
| `orders/create`, `orders/<id>/update` | Commander un plat, le modifier |
| `admin/results` | Récapitulatif par table |
| `gallery` | Images de la galerie |

## Lancer le projet en local

```bash
# API
cd backend
python -m venv venv
source venv/bin/activate        # Windows : venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

# Interface (dans un autre terminal)
cd frontend
yarn install
yarn start
```

Couleurs du projet : or `#D4AF37` et vert sapin `#0F2F20`. Polices : Cormorant Garamond et Outfit.

## Auteure

**Goyéli Rose Tuo**, développeuse d'applications web et mobile. [Mon portfolio](https://rtuo1978-a11y.github.io/PortfolioRose/)
