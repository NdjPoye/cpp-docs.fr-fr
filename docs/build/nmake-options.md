---
title: "Options de NMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "programme NMAKE, options"
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options de NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les options de NMAKE sont décrites dans le tableau ci\-après.  Ces options sont précédées par une barre oblique \(\/\) ou un tiret \(–\) et ne respectent pas la casse.  Utilisez [\!CMDSWITCHES](../build/makefile-preprocessing-directives.md) pour modifier les paramètres des options d'un makefile ou Tools.ini.  
  
|Option|Objectif|  
|------------|--------------|  
|\/A|Force la génération de toutes les cibles évaluées, même quand elles ne sont pas obsolètes par rapport aux dépendants.  Ne force pas la génération de cibles non apparentées.|  
|\/B|Force la génération même quand les horodatages coïncident.  Recommandée uniquement pour les systèmes très rapides \(résolution de deux secondes au plus\).|  
|\/C|Supprime la sortie par défaut, notamment les avertissements et les erreurs NMAKE récupérables, les horodatages et le message de copyright de NMAKE.  Supprime les avertissements émis par l'option \/K.|  
|\/D|Affiche les horodatages de chaque cible et dépendant évalués ainsi qu'un message quand aucune cible n'existe.  Cette option est utile avec l'option \/P pour le débogage d'un makefile.  Utilisez **\!CMDSWITCHES** pour définir ou supprimer l'option \/D pour une partie d'un makefile.|  
|\/E|Les variables d'environnement substituent les définitions de macros du makefile.|  
|\/ERRORREPORT\[NONE &#124; PROMPT &#124; QUEUE &#124; SEND \]|Si nmake.exe échoue au moment de l'exécution, vous pouvez utiliser \/ERRORREPORT pour envoyer des informations à Microsoft à propos de ces erreurs internes.<br /><br /> Pour plus d'informations sur \/ERRORREPORT, consultez [\/errorReport \(Signaler les erreurs internes du compilateur\)](../build/reference/errorreport-report-internal-compiler-errors.md).|  
|\/F `filename`|Spécifie `filename` en tant que makefile.  Des espaces ou des tabulations peuvent précéder `filename`.  Spécifiez l'option \/F une fois pour chaque makefile.  Pour fournir un makefile à partir d'une entrée standard, spécifiez un tiret \(–\) pour `filename`, puis terminez l'entrée au clavier par F6 ou CTRL\+Z.|  
|\/G|Affiche les makefiles inclus dans la directive \!INCLUDE.  Pour plus d'informations, consultez [Directives de prétraitement d'un makefile](../build/makefile-preprocessing-directives.md).|  
|\/HELP, \/?|Affiche un bref rappel de la syntaxe de la ligne de commande NMAKE.|  
|\/I|Ignore les codes de sortie de toutes les commandes.  Pour définir ou supprimer l'option \/I pour une partie d'un makefile, utilisez **\!CMDSWITCHES**.  Pour ignorer les codes de sortie dans une partie d'un makefile, utilisez un modificateur de commande tiret \(–\) ou [.IGNORE](../build/dot-directives.md).  Substitue l'option \/K si les deux options sont définies.|  
|\/K|Poursuit la génération de dépendants non apparentés, si une commande retourne une erreur.  Émet également un avertissement et retourne un code de sortie égal à 1.  Par défaut, NMAKE s'arrête si une commande retourne un code de sortie différent de zéro.  Les avertissements émis par l'option \/K sont supprimés par \/C ; \/I substitue \/K, si les deux options sont définies.|  
|\/N|Affiche les commandes, mais ne les exécute pas ; les commandes de prétraitement sont exécutées.  N'affiche pas les commandes dans les appels récursifs de NMAKE.  Pratique pour le débogage de makefiles et le contrôle des horodatages.  Pour définir ou supprimer l'option \/N pour une partie d'un makefile, utilisez **\!CMDSWITCHES**.|  
|\/NOLOGO|Supprime le message de copyright de NMAKE.|  
|\/P|Affiche des informations \(définitions de macros, règles d'inférence, cibles, liste [.SUFFIXES](../build/dot-directives.md)\) relatives aux entrées standard, puis exécute la génération.  Affiche des informations seulement en l'absence d'un makefile et d'une cible de ligne de commande.  À associer à l'option \/D pour déboguer un makefile.|  
|\/Q|Vérifie les horodatages des cibles ; n'exécute pas la génération.  Retourne un code de sortie zéro si toutes les cibles sont à jour et un code de sortie différent de zéro si une cible ne l'est pas.  Les commandes de traitement sont exécutées.  Utile lors de l'exécution de NMAKE à partir d'un fichier batch.|  
|\/R|Supprime la liste **.SUFFIXES** et ignore les règles d'inférence et les macros qui sont définies dans le fichier Tools.ini ou qui sont prédéfinies.|  
|\/S|Supprime l'affichage des commandes exécutées.  Pour supprimer l'affichage dans une partie d'un makefile, utilisez le modificateur de commande **@** ou [.SILENT](../build/dot-directives.md).  Pour définir ou supprimer l'option \/S pour une partie d'un makefile, utilisez **\!CMDSWITCHES**.|  
|\/T|Met à jour les horodatages des cibles de ligne de commande \(ou la première cible d'un makefile\) et exécute les commandes de prétraitement mais n'exécute pas la génération.|  
|\/U|Cette option doit être utilisée avec \/N.  Effectue un dump des fichiers NMAKE inline afin que la sortie de \/N puisse être utilisée en tant que fichier de commandes.|  
|\/X `filename`|Envoie la sortie d'erreur NMAKE à `filename` à la place d'une erreur standard.  Des espaces ou des tabulations peuvent précéder `filename`.  Pour envoyer une sortie d'erreur à une sortie standard, spécifiez un tiret \(–\) pour `filename`.  Cette option n'affecte pas la sortie des commandes vers l'erreur standard.|  
|\/Y|Désactive les règles d'inférence en mode batch.  Quand cette option est sélectionnée, toutes les règles d'inférence en mode batch sont traitées en tant que règles d'inférence ordinaires.|  
  
## Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)