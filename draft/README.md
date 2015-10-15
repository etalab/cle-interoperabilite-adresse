# Clé d'interopérabilité de l'adresse

Les termes DOIT, NE DOIT PAS, DEVRAIT, NE DEVRAIT PAS, PEUT, OBLIGATOIRE,
RECOMMANDÉ, OPTIONNEL ont un sens précis. Ils correspondent à la traduction
française de la norme [RFC2119](http://www.ietf.org/rfc/rfc2119.txt) des termes
respectifs MUST, MUST NOT, SHOULD, SHOULD NOT, MAY, REQUIRED, RECOMMENDED et
OPTIONAL.

## Objectif

Cette spécification décrit la normalisation d'une clé permettant l'échange de
données sur une adresse entre différentes bases dédiées. Seules les adresses
françaises sont couvertes.

## Format

La clé DOIT contenir les quatre éléments suivants, séparés par des
*underscores* (_):

* le code INSEE de la commune (OBLIGATOIRE)
* le code FANTOIR de la voie ou du lieu-dit, en lettres capitales (OBLIGATOIRE,
  se référer à «Format temporaire» pour le cas où FANTOIR n'est pas attribué)
* numéro de l'adresse (OPTIONNEL)
* indice de répétition complet (voir premier exemple), en lettres capitales sans signe diacritique
  ni aucun caractère non alphanumérique (OPTIONNEL)

Les éléments vides DOIVENT être présents dans la clé sous forme d'emplacements
vides.

## Exemples

* 18 bis, rue de Citeaux 21700 Agencourt : 21001_0022B_18_BIS
* 64, allée de Bercy 75012 Paris : 75112_0874E_64_
* Lieu-dit «Derrière Froid Cul», 54730 Ville-Houdlémont: 54572_B021S__

## Format temporaire

Le cas où une adresse existe mais son code FANTOIR n'a pas été attribué sera
géré par le «format temporaire». Le «format temporaire» remplace l'élément
FANTOIR par un élément temporaire composé comme suit:

* un dièse (#), signe distinctif de la clé temporaire (OBLIGATOIRE)
* le nom de la voie ou du lieu-dit (OBLIGATOIRE), normalisé selon les règles
  suivantes:
    - NE DOIT PAS contenir de signe diacritique
    - NE DOIT PAS contenir de caractère non alphanumérique
    - DOIT être tout en lettres capitales
    - les nombres DEVRAIENT être écrits en chiffres
    - DOIT être capé à 50 caractères

### Exemples

* 18 ter rue des Pêchers 75012 Paris: 75112_#RUEDESPECHERS_18_TER
* 22 allées du 14 Juillet 1789 75012 Paris: 75112_#ALLEESDU14JUILLET1789_22_
