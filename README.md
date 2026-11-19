# Démarrer avec Django 5.2 sous Python 3.14

Deux approches pour initialiser un projet Django 5.2 avec Python 3.14 sous Windows.

## Structure du dépôt

`
├── methode_pip/      # Méthode classique avec pip + venv
└── methode_uv/       # Méthode moderne avec uv (recommandé)
`

## Méthode A : pip + venv (classique)

La méthode standard, compatible partout.

`powershell
cd methode_pip
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
`

## Méthode B : uv (recommandé)

Plus rapide, gestion moderne des dépendances via `pyproject.toml` et `uv.lock`.

`powershell
cd methode_uv
uv sync
uv run python manage.py migrate
uv run python manage.py runserver
`

## Prérequis

- Python 3.14+
- [uv](https://docs.astral.sh/uv/) (pour la méthode B)

## Notes

- Les deux méthodes créent un projet Django identique avec une application `myfirstapp`
- La base de données SQLite n'est pas incluse dans le dépôt (générée au `migrate`)
- Le fichier `config/settings.py` contient une `SECRET_KEY` de développement uniquement
