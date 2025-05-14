# La Micro-Doc

    Le but de ce document est de documenter mes découvertes et ma compréhension du code source et est à destination de quiconque en aurait besoin incluant moi-même. Il n'a pas vocation à être exhaustif ni même détaillé mais permet plutôt d'avoir rapidement idée de comment est organisé le présent logiciel. 

**cmd** Le logiciel étant en ligne de commandes, la majorité du code (et le plus important dans mon cas) se trouve dans le dossier **cmd**. 
Chaque fichier go a un doublon associé nommé commmand_test.go. Utilité à définir. 
Les commandes s'ajoutent via la ligne ```RootCmd.AddCommand()``` situé dans le init. 
Les flags s'ajoutent de la même manière mais dans une sous liste ```ListRootCmd.AddCommand()``` par exemple pour les sous-listes. 

**client** (pour azure client) Semble gérer tout ce qui est call aux API (Graph API notamment). Les commandes situés dans **cmd** en appelle les fonctions et appliquent les filtres adéquats.
(exemple de list_group qui va bien appeler tout les groupes d'Intra mais ne va conserver que les groupes "securityEnabled")

**config** Et plus particulièrement config.go contient une bonne partie des commandes de configurations (notamment les différents commandes et flags pour se log).

**constants** Conserve des constantes utiles

**logger** Relatif aux logs, pas (encore) utile dans mon cas. 

**models** définit le modèle des données, lesquelles seront stockées une fois extraites (généralement modèle de base du repo Azure + TenantId et TenantName).

**panicrecovery** Relatif à la gestion des erreurs.

