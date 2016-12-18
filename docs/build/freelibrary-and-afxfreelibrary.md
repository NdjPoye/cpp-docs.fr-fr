---
title: "FreeLibrary et AfxFreeLibrary | Microsoft Docs"
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
  - "FreeLibrary"
  - "AfxFreeLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL d’extension [C++], déchargement"
  - "AfxFreeLibrary, méthode"
  - "décharger des DLL"
  - "FreeLibrary, méthode"
  - "DLL [C++], liaison"
  - "liaison explicite [C++]"
  - "DLL [C++], déchargement"
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# FreeLibrary et AfxFreeLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les processus qui lient de manière explicite à une DLL appellent la fonction [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188) quand le module de la DLL n'est plus nécessaire.  Cette fonction décrémente le décompte de référence du module et, si le comptage de référence indique zéro, annule son mappage dans l'espace d'adressage du processus.  
  
 Dans une application MFC, utilisez [AfxFreeLibrary](../Topic/AfxFreeLibrary.md) au lieu de `FreeLibrary` pour décharger une extension DLL.  L'interface \(prototype de fonction\) de `AfxFreeLibrary` est identique à celle de `FreeLibrary`.  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [LoadLibrary et AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../Topic/AfxFreeLibrary.md)