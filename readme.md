# Gestion d'inventaire

Programme de gestion d'inventaire minimal, avec une base de données.

## Prérequis & conseils

Ce programme est en développement actif, et ne devrait être utilisé que

- Si vous avez une bonne idée de la structure du programme;
- Si vous êtes capable de lire et déboguer du [Python]
- Si vous avez [Python] d'installé, avec les modules décrits dans `requirements.txt`
- Si vous pouvez utiliser [Git]

**Pour toutes questions, svp envoyez un courriel à [emile.jetzer@polymtl.ca] avec «_[gestion-inventaire]_» dans le sujet du courriel.

[Python]: https://www.python.org
[Git]: https://git-scm.com/
[emile.jetzer@polymtl.ca]: mailto:emile.jetzer@polymtl.ca?subject=[gestion-inventaire]

### Tag `v1`

La version `v1` est stable et peut-être utilisée telle quelle.

### Branche `alpha`

La branche `alpha` est en développement constant, et ne devrait pas être utilisée pour développer un programme plus ocmplexe.

### Branche `beta`

La branche `beta` est toujours fonctionnelle, mais peut changer d'un `commit` à l'autre dans les interfaces de classe, fonctionnalités, etc.

## Modules

1. `outils` comprend différents modules utilitaires.
    1. `config.py` contient une interface facilitant la manipulation de fichiers de configuration.
    2. `database` comprend des outils de manipulation de base de données.
        1. `__init__.py` comprend la classe `BaseDeDonnées` incluant le gros des fonctionnalités, y compris une interface entre SQLAlchemy et Pandas.
        2. `dtypes.py` comprend des fonctions de correspondance des types de données entre SQLAlchemy, Pandas, tkinter et Python.
        3. `gestion.py` contiendra des fonctions de migration de base de données.
    3. `interface` comprend des modules d'affichage.
        1.  `df.py` facilite l'affichage de bases de données comme tableurs ou formulaires.
        2. `onglets.py` facilite l'affichage de plusieurs bases de données et fichiers de configuration.
        3. `tkinter.py` facilite l'utilisation des classes tkinter.
        4. `html.py` facilitera bientôt l'affichage en html.
2. `heures` contient une ébauche de programme de gestion des heures.
3. `inventaire` contient une ébauche de programme d'inventaire.
4. `demo.py` est un script d'exemple des fonctionnalités du programme.

## Configuration

Le fichier de configuration `base.cfg` comporte différentes sections:

1. `bd` contient les informations sur la base de données et les tables de données à utiliser.
2. `tkinter` liste des paramètres de configuration de l'affichage.
3. Les autres sections décrivent différentes tables de données.

### `bd`

1. `adresse` indique la position du fichier de base de données, et le protocole SQLAlchemy à utiliser. En ce moment n'utilisez que `sqlite`, qui stocke la base de données dans un fichier localement.
2. `tables` est une énumération ligne par ligne des tableaux de base de données à afficher.
3. `formulaires` est une énumération ligne par ligne des tableaux pour lesquels afficher des formulaires.

### `tkinter`

1. `title` donne le titre de la fenêtre principale.

# À faire

- [ ] Permettre l'ajout de colonnes de l'intérieur de l'application
- [ ] Permettre d'effacer des rangées
- [ ] Permettre d'ajouter des sections de configuration
- [ ] Permettre d'ajouter des champs de configuration
- [ ] Placer la base de données dans son propre répertoire git externe, et automatiquement en faire des sauvegardes
- [ ] Faciliter l'importation de documents Excel & d'autres bases de données