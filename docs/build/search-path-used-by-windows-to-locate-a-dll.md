---
title: "Chemin de recherche utilis&#233; par Windows pour localiser une DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL (C++), chemin de recherche Windows"
  - "rechercher des DLL"
  - "recherches de DLL connus (C++)"
  - "localiser des DLL"
  - "chemin de recherche (C++)"
  - "rechercher (C++), DLL"
  - "Windows (C++), chemin de recherche de DLL"
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Chemin de recherche utilis&#233; par Windows pour localiser une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec une liaison à la fois implicite et explicite, Windows recherche d'abord les « DLL connues », telles que Kernel32.dll et User32.dll.  Windows recherche ensuite les DLL dans les emplacements suivants selon l'ordre indiqué :  
  
1.  Le répertoire contenant le module exécutable du processus en cours.  
  
2.  Le répertoire actif.  
  
3.  Le répertoire System de Windows.  La fonction **GetSystemDirectory** récupère le chemin de ce répertoire.  
  
4.  Le répertoire Windows.  La fonction **GetWindowsDirectory** récupère le chemin de ce répertoire.  
  
5.  Les répertoires désignés dans la variable d'environnement PATH.  
  
    > [!NOTE]
    >  La variable d'environnement LIBPATH n'est pas utilisée.  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Lier de manière explicite](../build/linking-explicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)