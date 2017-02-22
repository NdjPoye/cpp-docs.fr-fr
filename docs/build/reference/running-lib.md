---
title: "Ex&#233;cution de LIB | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.TargetMachine"
  - "Lib"
  - "VC.Project.VCLibrarianTool.PrintProgress"
  - "VC.Project.VCLibrarianTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ (fichiers de commandes)"
  - "/MACHINE (option de plate-forme cible)"
  - "/NOLOGO (option du Gestionnaire de bibliothèque)"
  - "/VERBOSE (option du Gestionnaire de bibliothèque)"
  - "signe deux-points (fichiers de commandes)"
  - "fichiers de commandes"
  - "fichiers de commandes, LIB"
  - "tiret (spécificateur d'option)"
  - "spécificateur d'option à barre oblique"
  - "LIB (C++), exécuter LIB"
  - "MACHINE (option de plate-forme cible)"
  - "-MACHINE (option de plate-forme cible)"
  - "NOLOGO (option du Gestionnaire de bibliothèque)"
  - "-NOLOGO (option du Gestionnaire de bibliothèque)"
  - "point-virgule, fichiers de commandes"
  - "barre oblique (/)"
  - "VERBOSE (option du Gestionnaire de bibliothèque)"
  - "-VERBOSE (option du Gestionnaire de bibliothèque)"
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ex&#233;cution de LIB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diverses options de ligne de commande permettent de gérer LIB.  
  
## Ligne de commande LIB  
 Pour exécuter LIB, tapez la commande `lib` suivie des noms des options et des fichiers correspondant à la tâche que vous cherchez à exécuter à l'aide de LIB.  LIB accepte également les entrées de ligne de commande effectuées dans les fichiers de commandes, qui sont décrites dans la section suivante.  LIB n'utilise pas de variable d'environnement.  
  
> [!NOTE]
>  Si vous êtes familiarisé avec les outils LINK32.exe et LIB32.exe fournis dans le Kit de développement logiciel \(SDK\) Microsoft Win32 pour Windows NT, vous avez peut\-être déjà l'habitude d'utiliser la commande `link32 -lib` ou la commande `lib32` pour gérer les bibliothèques et créer des bibliothèques d'importation.  Veillez à modifier les makefiles et batch pour utiliser plutôt la commande `lib`.  
  
## Fichiers de commandes LIB  
 Vous pouvez passer des arguments de ligne de commande à LIB dans un fichier de commandes en utilisant la syntaxe suivante :  
  
```  
LIB @commandfile  
```  
  
 Le fichier `commandfile` est un fichier texte.  Les espaces et les tabulations sont interdits entre le signe arobase \(@\) et le nom de fichier.  Il n'existe pas d'extension par défaut ; vous devez spécifier le nom de fichier complet, y compris l'extension éventuellement.  Les caractères génériques ne sont pas autorisés.  Vous pouvez spécifier un chemin absolu ou relatif avec le nom de fichier.  
  
 Dans le fichier de commandes, les arguments peuvent être séparés par des espaces ou des tabulations, comme c'est le cas sur la ligne de commande ; ils peuvent également être séparés par des caractères de saut de ligne.  Utilisez un point\-virgule \(;\) pour signaler un commentaire.  LIB ignore tout le texte compris entre le point\-virgule et la fin de la ligne.  
  
 Vous pouvez spécifier tout ou partie de la ligne de commande dans un fichier de commandes, et vous pouvez utiliser plusieurs fichiers de commandes dans une commande LIB.  LIB accepte l'entrée du fichier de commandes comme si elle était spécifiée à cet emplacement sur la ligne de commande.  Les fichiers de commandes ne peuvent pas être imbriqués.  LIB reproduit par écho le contenu des fichiers de commandes quand l'option \/NOLOGO n'est pas utilisée.  
  
## Utilisation des options LIB  
 Une option est constituée d'un spécificateur d'option, qui peut être un tiret \(–\) ou une barre oblique \(\/\) suivi\(e\) du nom de l'option.  Les noms des options ne peuvent pas être abrégés.  Certaines options acceptent un argument spécifié après le signe deux\-points \(:\).  Les espaces et les tabulations sont interdits dans la spécification d'une option.  Utilisez des espaces ou des tabulations pour séparer les spécifications des options sur la ligne de commande.  Les noms des options et leurs arguments \(mots clés ou noms de fichiers\) ne respectent pas la casse, mais les identificateurs utilisés comme arguments la respectent.  LIB traite les options dans l'ordre spécifié sur la ligne de commande et dans les fichiers de commandes.  Si une option est répétée avec différents arguments, le dernier argument traité est prioritaire.  
  
 Les options suivantes s'appliquent à tous les modes de LIB :  
  
 \/ERRORREPORT\[NONE &#124; PROMPT &#124; QUEUE &#124; SEND \]  
 Si lib.exe échoue au moment de l'exécution, vous pouvez utiliser \/ERRORREPORT pour envoyer des informations à Microsoft à propos de ces erreurs internes.  
  
 Pour plus d'informations sur \/ERRORREPORT, consultez [\/errorReport \(Signaler les erreurs internes du compilateur\)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 \/LTCG  
 Entraîne la génération de la bibliothèque à l'aide de la génération du code au moment de la liaison.  Pour plus d'informations, consultez [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 \/MACHINE  
 Spécifie la plateforme cible du programme.  En règle générale, il n'est pas nécessaire de spécifier \/MACHINE.  LIB déduit le type d'ordinateur à partir des fichiers .obj.  Cependant, dans certaines circonstances, LIB ne peut pas déterminer le type d'ordinateur et émet un message d'erreur.  Si une telle erreur se produit, spécifiez \/MACHINE.  En mode \/EXTRACT, cette option est destinée à des fins de vérification uniquement.  Utilisez `lib /?` sur la ligne de commande pour afficher les types d'ordinateur disponibles.  
  
 \/NOLOGO  
 Supprime l'affichage du message de copyright et du numéro de version de LIB, et empêche la reproduction par écho des fichiers de commandes.  
  
 \/VERBOSE  
 Affiche des détails relatifs à la progression de la session, notamment les noms des fichiers .obj qui sont ajoutés.  Les informations sont envoyées vers la sortie standard et peuvent être redirigées vers un fichier.  
  
 \/WX\[:NO\]  
 Considère les avertissements comme des erreurs.  Pour plus d'informations, consultez [\/WX \(Traiter les avertissements de l'Éditeur de liens comme des erreurs\)](../../build/reference/wx-treat-linker-warnings-as-errors.md).  
  
 D'autres options s'appliquent uniquement à des modes spécifiques de LIB.  Ces options sont traitées dans les sections décrivant chaque mode.  
  
## Voir aussi  
 [Référence LIB](../../build/reference/lib-reference.md)