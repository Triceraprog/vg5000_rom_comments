# Commentaires de la ROM VG5000µ

Les deux fichiers sont les commentaires de la `ROM`s de l'ordinateur 8 bits VG5000µ en versions 1.0 et 1.1.

## Format des fichiers

Ces fichiers ont le format suivant :

- Dans les 11 premières colonnes est placée l'adresse ou la plage d'adresse sur laquelle le commentaire s'applique.
- À partir de la colonne 13 sont placés les commentaires.
- Un nom entre crochets désigne un `label`, c'est-à-dire une adresse nommée.
- Le caractère `%` indique des méta-indications.
    - `CODE` indique qu'il s'agit d'une section contenant du code exécutable, même si aucun saut apparent n'est fait à cette adresse.
    - `SECTION` indique le début d'une section telle qu'indiquée dans le manuel technique.
    - `NTS` indique une « Null Terminated String » dans les données.
    - `MS\_BASIC` indique entre parenthèse un label correspondant dans le BASIC NASCOM. L'indication n'est pas systématique.
    - `CHAR` indique que le paramètre numérique de l'opcode est un caractère.
    - `NOT\_LABEL` indique que le paramètre numérique de l'opcode n'est pas une adresse de label, même si une adresse correspond.
    - `DATASKIP` indique que l'octet n'est pas une instruction et doit être ignoré. C'est le cas après chaque `rst $8`, qui cherche son paramètre dans l'octet qui suit.
- Lorsqu'un commentaire est associé à un label, il indique un commentaire général, qui s'affiche typiquement avant la routine.
- Lorsqu'un commentaire n'est pas associé à un label, il indique un commentaire sur les lignes indiquées par l'adresse ou la plage d'adresses.
Exemple :
```
    $0000       [reset]
                Ce commentaire est associé au label `reset`.

    $0000       Ce commentaire est associé à l'adresse $0000.
    $0010-$0011 Ce commentaire est associé à la plage d'adresses $0010 à $0011 incluses.
```

## Remarque sur les nommages

Lorsqu'un label possède un nom dans une documentation du VG5000µ, comme le manuel technique, celui-ci est conservé.

