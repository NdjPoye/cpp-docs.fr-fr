---
title: "/BIND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/BIND (option Editbin)"
  - "BIND (option Editbin)"
  - "-BIND (option Editbin)"
  - "points d'entrée"
  - "points d'entrée, adresses"
  - "table des adresses d'importation"
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /BIND
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/BIND[:PATH=path]  
```  
  
## Notes  
 Cette option définit les adresses des points d'entrée dans la table des adresses d'importation pour un fichier exécutable ou une DLL.  Utilisez cette option pour réduire le temps de chargement d'un programme.  
  
 Spécifiez le fichier exécutable et les DLL du programme dans l'argument *files* sur la ligne de commande EDITBIN.  L'argument facultatif *path* de \/BIND spécifie l'emplacement des DLL utilisées par les fichiers spécifiés.  Séparez les répertoires multiples par un point\-virgule \(**;**\).  Si *path* n'est pas spécifié, EDITBIN parcourt les répertoires spécifiés dans la variable d'environnement PATH.  Si *path* est spécifié, EDITBIN ignore la variable PATH.  
  
 Par défaut, le chargeur de programme définit les adresses des points d'entrée au moment de charger un programme.  La durée de ce processus varie en fonction du nombre de DLL et du nombre de points d'entrée référencés dans le programme.  Si un programme a été modifié à l'aide de l'option \/BIND et si les adresses de base du fichier exécutable et de ses DLL n'entrent pas en conflit avec les DLL déjà chargées, le système d'exploitation n'a pas besoin de définir ces adresses.  Si les fichiers reposent sur une base incorrecte, le système d'exploitation déplace les DLL du programme et recalcule les adresses des points d'entrée, ce qui a pour effet d'allonger la durée de chargement du programme.  
  
## Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)