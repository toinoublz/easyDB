# Module easyDB

Un module Python simple pour gérer une base de données JSON locale.

## Description

Le module DB permet de créer et d'interagir avec une base de données stockée au format JSON. Il offre une interface simple pour stocker, récupérer, mettre à jour et supprimer des données.

## Installation

1. Assurez-vous d'avoir Python 3.6 ou supérieur installé
2. Installez le module en utilisant pip :
   ```
   pip install -e .
   ```

## Utilisation

### Initialisation

```python
from easyDB import DB

# Créer une nouvelle instance de base de données
db = DB("ma_base_de_donnees")
```

### Méthodes disponibles

- `get(nom)`: Récupère une valeur par sa clé
- `set(nom, valeur)`: Définit une valeur pour une clé donnée
- `delete(nom)`: Supprime une entrée de la base de données
- `get_all()`: Récupère toutes les entrées de la base de données
- `delete_all()`: Supprime toutes les entrées de la base de données

### Exemple complet

```python
from easyDB import DB

# Initialisation
db = DB("exemple")

# Ajouter des données
db.set("utilisateur", {"nom": "Jean", "age": 30})
db.set("config", {"theme": "sombre", "notifications": True})

# Récupérer des données
utilisateur = db.get("utilisateur")
print(utilisateur)  # Affiche: {'nom': 'Jean', 'age': 30}

# Supprimer une entrée
db.delete("config")

# Vérifier la suppression
config = db.get("config")
print(config)  # Affiche: None
```

## Structure des fichiers

```
easyDB/
├── DB/
│   ├── __init__.py
│   └── db.py          # Implémentation principale
├── json/              # Dossier où sont stockées les bases de données
│   └── *.db.json      # Fichiers de base de données
├── pyproject.toml     # Configuration du package
└── README.md          # Ce fichier
```

## Configuration

Le module peut être configuré avec les paramètres suivants lors de l'initialisation :

- `name` (obligatoire) : Nom de la base de données (sans extension)
- `verbose` (optionnel, True par défaut) : Active/désactive les messages de journalisation
- `indent` (optionnel, False par défaut) : Active/désactive l'indentation dans le fichier JSON

## Licence

Ce projet est sous licence MIT.
