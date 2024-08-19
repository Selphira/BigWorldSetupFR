[![Github Releases](https://img.shields.io/github/v/release/Selphira/BigWorldSetupFR)](https://github.com/Selphira/BigWorldSetupFR/releases/latest)
![Langues](https://img.shields.io/static/v1?label=Langues&message=Français&color=limegreen)
![Jeux supportés](https://img.shields.io/static/v1?label=Jeux%20supportés&message=EET%20%7C%20BG2EE&color=dodgerblue)

# Big World Setup FR (BWS-FR)

Cette application est une modification du [Big World Setup](<https://github.com/BigWorldSetup/BigWorldSetup>).  
Tout comme ce dernier, elle vous permet de télécharger, extraire et installer automatiquement des mods, tout en gérant les conflits, dépendances et ordres d'installation.

Cette version ne gère que des mods compatibles avec EET possédant une traduction française. Quelques exceptions qui n'ont aucune conséquence sur les textes affichés sont toutefois tolérées.

## Pour commencer

1. [Télécharger](<https://github.com/Selphira/BigWorldSetupFR/archive/master.zip>) le Big World Setup FR.
2. L'extraire où vous voulez (mais pas dans le dossier du jeu !)
3. Fermer les jeux ouverts et les éditeurs de jeux pour éviter toute interférence avec le processus d'installation
4. Désactiver votre antivirus (uniquement pendant l'installation - n'oubliez pas de le réactiver après !)
5. Désactiver le contrôle des comptes d'utilisateur (UAC) (si vous ne le faites pas, l'installation automatisée peut se bloquer !)
6. Exécuter "BWS-FR.vbs" en double cliquant dessus.

## Mettre à jour l'application

Afin de vous assurer de toujours exécuter la version la plus récente, il suffit d'exécuter le fichier "BWS-FR update.vbs".  

## Le dossier "OverwriteFiles"
Parfois, vous devez écraser des fichiers de mod **APRÈS** leur extraction mais **AVANT** que "Big World Fixpack" n'applique ses corrections.  
Dans ce cas, vous pouvez placer tous les fichiers de mods personnalisés en utilisant exactement la même structure de dossiers.

BWS-FR s'en sert pour intégrer des fichiers de configuration utilisés par certains mods pour pré-configurer leur installation.  
Vous pouvez les modifier pour ajuster certains paramètres des mods à votre convenance. 

Par exemple pour Stratagems (stratagems\stratagems.ini), mettez votre fichier personnalisé "stratagems.ini" dans le dossier "BWP\stratagems" et il sera utilisé lors de l'installation.

### <a name="corrections"></a>Corrections intégrées

Divers correctifs pour améliorer la compatibilité ou corriger des bugs sont inclus automatiquement installés. Ils se trouvent dans un dans un dépôt à part : [BWS-FR Fixpack](<https://github.com/Selphira/BWS-FR-Fixpack>)

J'invite les auteurs des mods originaux à récupérer ces correctifs pour les intégrer dans leur version officielle (si toutefois la correction leur convient).

## Informations techniques

### Les types de mod
Le type général d'un mod renseigné dans son fichier ini permet de savoir dans quelle sélection automatique ils seront présent.
Il est possible de définir plusieurs types pour un mod, cela permettra de le faire apparaitre dans plusieurs sélections
automatique. (Ex: Type=F,R,S,T,E)
  
F : [F]ixe (Mods essentiels, ils ne pourront pas être désélectionnés)  
R : [R]ecommandé (Mods au contenu de haute qualité et bien intégré)  
S : Maximi[S]é (Mods de toutes qualités, excluant les contenus les plus difficiles)  
T : [T]actique (Mods de toutes qualités, incluant les contenus les plus difficiles)  
E : [E]xpert (Mods présentant des problèmes connus, pour le débogage)

Note : Pour le type Fixe, il est possible de faire en sorte que certains commposants ne soient pas fixés. Pour se faire,
il suffit d'ajouter l'option "NotFixed" dans la section [Mod] du fichier ini du mod concerné (Ex: NotFixed=1 2 10)

### Les  lignes d'installation

Un ligne du fichier InstallOrder.ini est composée de différentes sections

[LineType];[SetupName];[ComponentNumber];[Theme];[Defaults];[CompReq]  

LineType : Le type de la ligne d'installation  
SetupName : Le nom du mod à installer  
ComponentNumber : Le numéro du composant à installer  
Theme : La catégorie dans laquelle se trouve le composant  
Defaults : Les valeurs défaut pour correspondant respectivement aux types RSTE. Cela permet de pouvoir placer un
composant particulier dans une sélection différente du type général du mod.  
CompReq : ???

#### Les types de ligne d'installation

ANN : Un commentaire  
CMD : Une commande shell à exécuter  
DWN : Téléchargement d'un mod  
STD : Installation d'un composant  
MUC : Liste de choix de plusieurs composants différents, un seul peut être sélectionné    
SUB : Liste de choix pour un même composant, généralement car le composant nécessite une entrée manuelle, un seul peut être sélectionné
GRP : Permet d'installer plusieurs composants en une seule commande

#### Les catégories de ligne d'installation
00 : Général  
01 : Corrections  
02 : Gros mods: BG1  
03 : Quêtes: BG1  
04 : PNJs: BG1  
05 : Relatif aux PNJs: BG1  
06 : Rencontres tactiques: BG1  
07 : Règles et ajustements: BG1  
08 : Magasins et objets: BG1  
09 : Gros mods: BG2  
10 : Quêtes: BG2  
11 : Mini-Mods  
12 : PNJs: BG2  
13 : Petits PNJs: BG2  
14 : Relatif aux PNJs: BG2  
15 : Rencontres tactiques: BG2  
16 : Règles, ajustements et sorts: BG2  
17 : Magasins et objets: BG2  
18 : Intelligence artificielle  
19 : Kits  
20 : Interface  
21 : Graphisme, portraits et sons

## Remerciements

Un grand merci à toutes ces personnes pour leur aide dans l'amélioration de l'outil !

- [JohnBob](https://www.baldursgateworld.fr/memberlist.php?mode=viewprofile&u=16284)
- [Deratiseur](https://www.baldursgateworld.fr/memberlist.php?mode=viewprofile&u=8352)