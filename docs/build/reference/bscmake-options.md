---
title: "Options BSCMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCBscMakeTool.OutputFile"
  - "VC.Project.VCBscMakeTool.SuppressStartupBanner"
  - "VC.Project.VCBscMakeTool.PreserveSBR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/v BSCMAKE, option"
  - "Iu BSCMAKE, option"
  - "parcourir des fichiers d’informations (.bsc), contenu"
  - "/Er BSCMAKE, option"
  - "NOLOGO BSCMAKE, option"
  - "/s BSCMAKE, option"
  - "/Ei BSCMAKE, option"
  - "/o BSCMAKE, option"
  - "/NOLOGO BSCMAKE, option"
  - "/Iu BSCMAKE, option"
  - "s BSCMAKE, option (/s)"
  - "/Em BSCMAKE, option"
  - "Em BSCMAKE, option"
  - "Es BSCMAKE, option"
  - "fichiers [C++], BSCMAKE"
  - "Er BSCMAKE, option"
  - "BSCMAKE, options pour contrôler des fichiers"
  - "contrôler les options BSCMAKE"
  - "El BSCMAKE, option"
  - "/El BSCMAKE, option"
  - "/Es BSCMAKE, option"
  - "Ei BSCMAKE, option"
ms.assetid: fa2f1e06-c684-41cf-80dd-6a554835ebd2
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options BSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette section décrit les options dont vous disposez pour contrôler BSCMAKE.  Plusieurs options permettent de gérer le contenu du fichier d'informations de consultation en excluant ou incluant certaines informations.  Les options d'exclusion peuvent aboutir à une exécution plus rapide de BSCMAKE et à un fichier .bsc de plus petite taille.  Les noms d'options respectent la casse \(sauf **\/HELP** et **\/NOLOGO**\).  
  
 Dans l'environnement de développement Visual Studio, seules les options **\/NOLOGO** et **\/o** sont disponibles.  Pour plus d'informations sur la manière d'accéder aux propriétés d'un projet, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
 \/Ei \( `filename`...\)  
 Exclut du fichier d'informations de consultation le contenu des fichiers Include spécifiés.  Si vous spécifiez plusieurs fichiers à exclure, séparez leurs noms par un espace et entourez la liste de parenthèses.  Les parenthèses ne sont pas nécessaires si vous spécifiez un seul `filename`.  Utilisez **\/Ei** en plus de l'option **\/Es** pour exclure d'autres fichiers non exclus par **\/Es**.  
  
 \/El  
 Exclut les symboles locaux.  Par défaut, les symboles locaux sont inclus.  Pour plus d'informations sur les symboles locaux, consultez [Création d'un fichier .sbr](../../build/reference/creating-an-dot-sbr-file.md).  
  
 \/Em  
 Exclut les symboles des corps des macros.  Utilisez l'option **\/Em** pour inclure uniquement les noms de macros dans le fichier d'informations de consultation.  Par défaut, les noms des macros et le résultat de leur expansion sont inclus.  
  
 \/Er \(`symbol`...\)  
 Exclut du fichier d'informations de consultation les symboles spécifiés.  Si vous spécifiez plusieurs symboles à exclure, séparez leurs noms par un espace et entourez la liste de parenthèses.  Les parenthèses ne sont pas nécessaires si vous spécifiez un seul `symbol`.  
  
 \/Es  
 Exclut du fichier d'informations de consultation tous les fichiers Include spécifiés avec un chemin absolu ou placés sur un chemin absolu spécifié dans la variable d'environnement INCLUDE. \(Il s'agit généralement de fichiers Include système qui contiennent beaucoup d'informations probablement inutiles dans votre fichier d'informations de consultation.\) Cette option n'exclut pas les fichiers spécifiés sans chemin ou avec un chemin relatif, ni les fichiers situés dans un chemin relatif dans INCLUDE.  Il vous est possible d'utiliser l'option **\/Ei** en plus de l'option **\/Es** pour exclure des fichiers non exclus par **\/Es**.  Si vous souhaitez exclure une partie seulement des fichiers exclus par l'option **\/Es**, utilisez l'option **\/Ei** plutôt que **\/Es** et spécifiez les fichiers à exclure.  
  
 \/errorreport:\[none &#124; prompt &#124; queue &#124; send\]  
 Vous permet d'envoyer des informations à Microsoft concernant des erreurs internes liées à bscmake.exe.  
  
 Pour plus d'informations sur **\/errorreport**, consultez [\/errorReport \(Signaler les erreurs internes du compilateur\)](../../build/reference/errorreport-report-internal-compiler-errors.md).  
  
 \/HELP  
 Affiche un résumé de la syntaxe de la ligne de commande de BSCMAKE.  
  
 \/Iu  
 Inclut les symboles non référencés.  Par défaut, BSCMAKE ne retient pas les symboles qui sont définis mais pas référencés.  Si un fichier .sbr a été compressé, cette option n'a aucun effet sur ce fichier car le compilateur a déjà supprimé les symboles non référencés.  
  
 \/n  
 Force une génération non incrémentielle.  Utilisez **\/n** pour imposer une génération complète du fichier d'informations de consultation, qu'il existe ou non un fichier .bsc préalable, pour empêcher que les fichiers .sbr ne soient tronqués.  Consultez [Génération d'un fichier .bsc par BSCMAKE](../../build/reference/how-bscmake-builds-a-dot-bsc-file.md).  
  
 \/NOLOGO  
 Supprime le message de copyright de BSCMAKE.  
  
 \/o `filename`  
 Spécifie le nom du fichier d'informations de consultation.  Par défaut, BSCMAKE affecte au fichier d'informations de consultation le nom de base du premier fichier .sbr et ajoute l'extension .bsc.  
  
 \/S \( `filename`...\)  
 Indique à BSCMAKE de traiter le fichier Include spécifié lorsqu'il le rencontre pour la première fois et de l'exclure dans les autres cas.  Cette option permet de réduire le temps de traitement lorsqu'un fichier \(fichier d'en\-tête .h pour un fichier source .c ou .cpp\) est inclus dans plusieurs fichiers source mais que les directives de prétraitement le laissent à chaque fois inchangé.  Vous pouvez également recourir à cette option si un fichier est modifié d'une manière qui n'affecte pas le fichier d'informations de consultation que vous créez.  Si vous spécifiez plusieurs fichiers à exclure, séparez leurs noms par un espace et entourez la liste de parenthèses.  Les parenthèses ne sont pas nécessaires si vous spécifiez un seul `filename`.  Pour exclure le fichier chaque fois qu'il est inclus, utilisez l'option **\/Ei** ou **\/Es**.  
  
 \/v  
 Cette option permet d'obtenir une sortie détaillée comprenant le nom de chaque fichier .sbr traité et des informations sur le déroulement de BSCMAKE.  
  
 \/?  
 Affiche un bref résumé de la syntaxe de la ligne de commande de BSCMAKE.  
  
 La ligne de commande suivante prescrit à BSCMAKE d'effectuer une génération complète de MAIN.bsc à partir de trois fichiers .sbr.  Elle indique également que les instances en double de TOOLBOX.h doivent être exclues.  
  
```  
BSCMAKE /n /S toolbox.h /o main.bsc file1.sbr file2.sbr file3.sbr  
```  
  
## Voir aussi  
 [Référence BSCMAKE](../../build/reference/bscmake-reference.md)