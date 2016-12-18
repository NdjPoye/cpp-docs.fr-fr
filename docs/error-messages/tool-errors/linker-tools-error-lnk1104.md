---
title: "Erreur des outils &#201;diteur de liens LNK1104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1104"
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 8
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d’ouvrir le fichier « nomfichier »  
  
 L’outil n’a pas pu ouvrir le fichier donné.  
  
 Les causes possibles sont les suivantes :  
  
-   L’espace disque est insuffisant.  
  
-   Le fichier n'existe pas.  
  
-   Quand vous spécifiez des bibliothèques dans la boîte de dialogue des pages de propriétés d’un projet, vous devez séparer les noms des bibliothèques par des espaces \(et non par des virgules\).  
  
-   Le nom de fichier ou le chemin d’accès est incorrect.  
  
-   La spécification du lecteur n’est pas valide.  
  
-   Les autorisations sur les fichiers sont insuffisantes.  
  
-   Le chemin d’accès de `filename` s’étend sur plus de 260 caractères.  
  
-   Si le fichier se nomme `LNKn`, qui est un nom de fichier généré par l’éditeur de liens pour un fichier temporaire, le répertoire spécifié dans la variable d’environnement TMP peut ne pas exister, ou plusieurs répertoires sont spécifiés pour la variable d’environnement TMP. \(Vous ne devez spécifier qu’un seul chemin d’accès de répertoire pour la variable d’environnement TMP.\)  
  
-   Si le message d’erreur s’affiche pour un nom de bibliothèque et que vous avez porté récemment le fichier .mak à partir d’un système de développement Microsoft Visual C\+\+ antérieur, la bibliothèque n’est peut\-être plus valide. Dan ce cas, assurez\-vous que la bibliothèque existe toujours.  
  
-   Un autre programme a peut\-être ouvert le fichier et l’éditeur de liens ne peut pas y accéder en écriture.  
  
-   La variable d’environnement LIB est incorrecte. Pour plus d’informations sur la façon de mettre à jour la variable d’environnement LIB, consultez [Page de propriétés Répertoires VC\+\+](../../ide/vcpp-directories-property-page.md). Assurez\-vous que tous les répertoires contenant les bibliothèques dont vous avez besoin sont répertoriés ici.  
  
 L’éditeur de liens utilise des fichiers temporaires dans plusieurs cas. Même si vous disposez d’un espace disque suffisant, un lien très volumineux peut épuiser ou fragmenter l’espace d’adressage.  
  
 Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
-   Utilisez [\/OPT \(Optimisations\)](../../build/reference/opt-optimizations.md). L’élimination comdat transitive lit tous les fichiers objets plusieurs fois.  
  
-   Effectuez la mise à niveau vers Windows XP.