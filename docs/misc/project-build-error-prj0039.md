---
title: "Erreur de g&#233;n&#233;ration de projet PRJ0039 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PRJ0039"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0039"
ms.assetid: 207bbc28-922f-44d6-8bdd-3016c850f5b9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# Erreur de g&#233;n&#233;ration de projet PRJ0039
Impossible de créer un fichier temporaire. Ce fichier doit pouvoir être créé pour que l’outil NMake puisse s’exécuter.  
  
 Lors de la génération d’un projet Makefile \(consultez [Création d’un projet Makefile](../ide/creating-a-makefile-project.md)\), le système du projet Visual C\+\+ doit créer quelques fichiers temporaires. Cette erreur indique que le système du projet n’a pas pu créer un ou plusieurs de ces fichiers.  
  
 La variable d’environnement TMP contient le nom du répertoire temporaire.  
  
 Les causes éventuelles de cette erreur et les solutions suggérées sont répertoriées ci\-dessous :  
  
 L’utilisateur ne dispose pas d’un accès en écriture au répertoire temporaire  
 Assurez\-vous de disposer d’un accès en écriture au répertoire temporaire.  
  
 Trop de fichiers temporaires dans le répertoire temporaire  
 D’autres processus ont peut\-être créé des fichiers temporaires, mais ne les ont pas supprimés. Supprimez certains fichiers temporaires ou la totalité.  
  
 Espace disque insuffisant  
 Supprimez quelques fichiers sur votre disque ou déplacez votre répertoire temporaire vers un disque disposant d’espace.  
  
 La variable d’environnement TMP est incorrecte  
 La variable d’environnement TMP peut pointer vers un répertoire qui n’existe pas.