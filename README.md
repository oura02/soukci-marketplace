# 🛍️ SoukCI - Marketplace des Artisans Ivoiriens

Plateforme e-commerce Django complète avec catalogue, panier, paiement Wave/Orange Money (simulation), dashboard vendeur et gestion des commandes.

## 🚀 Installation rapide

```bash
cd marketplace
python -m venv env
source env/bin/activate       # Linux/Mac
env\Scripts\activate          # Windows

pip install -r requirements.txt

python manage.py makemigrations
python manage.py migrate
python manage.py loaddata shop/fixtures/categories.json
python manage.py createsuperuser
python manage.py runserver
```

## 🌐 URLs

| URL | Description |
|-----|-------------|
| `/` | Page d'accueil |
| `/shop/` | Catalogue produits |
| `/shop/produit/<slug>/` | Détail produit |
| `/shop/panier/` | Panier |
| `/orders/checkout/` | Passer une commande |
| `/orders/paiement/<ref>/` | Paiement mobile money |
| `/orders/mes-commandes/` | Mes commandes (acheteur) |
| `/orders/vendeur/commandes/` | Commandes reçues (vendeur) |
| `/dashboard/` | Dashboard (vendeur ou acheteur) |
| `/dashboard/mes-produits/` | Gérer ses produits |
| `/accounts/register/` | Inscription vendeur/acheteur |
| `/admin/` | Administration |

## 📁 Structure

```
marketplace/
├── marketplace/       # Config principale
├── accounts/          # Auth + profils
├── shop/              # Produits, catégories, panier
│   ├── models.py      → Produit, Categorie, Panier, ProfilVendeur
│   ├── views.py       → Catalogue, panier, détail
│   └── fixtures/categories.json
├── orders/            # Commandes + paiement
│   └── models.py      → Commande, LigneCommande, Paiement
├── dashboard/         # Dashboard vendeur/acheteur
└── templates/
    ├── base.html
    ├── home.html
    ├── shop/
    ├── orders/
    ├── dashboard/
    └── accounts/
```

## 💳 Paiements simulés

Le système simule Wave, Orange Money et MTN Money. En production, intégrer :
- **Wave CI** : https://wave.com/en/africa/developers/
- **Orange Money CI** : API Orange Money Côte d'Ivoire
- **MTN MoMo** : https://momodeveloper.mtn.com/

## 🔜 Évolutions possibles

- Intégration API Wave réelle
- Système de messagerie vendeur/acheteur
- Évaluations et avis produits
- Livraison avec suivi GPS
- Application mobile (Flutter/React Native)
  
