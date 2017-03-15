---
title: "LoadLibrary et AfxLoadLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxLoadLibrary (méthode)"
  - "DLL (C++), AfxLoadLibrary"
  - "DLL (C++), LoadLibrary"
  - "liaison explicite (C++)"
  - "LoadLibrary (méthode)"
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# LoadLibrary et AfxLoadLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les processus appellent [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) \(ou [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)\) pour établir une liaison explicite avec une DLL.  Si la fonction réussit, elle mappe la DLL spécifiée à l'espace d'adressage du processus appelant et retourne un handle vers la DLL qui peut être utilisé avec d'autres fonctions pour une liaison explicite, par exemple, `GetProcAddress` et `FreeLibrary`.  
  
 `LoadLibrary` tente de localiser la DLL à l'aide de la séquence de recherche utilisée pour la liaison implicite.  Si le système ne trouve pas la DLL ou si la fonction de point d'entrée retourne FALSE, `LoadLibrary` retourne NULL.  Si l'appel à `LoadLibrary` spécifie un module DLL qui est déjà mappé à l'espace d'adressage du processus appelant, la fonction retourne un handle vers la DLL et incrémente le décompte de références du module.  
  
 Si la DLL a une fonction de point d'entrée, le système d'exploitation appelle la fonction dans le contexte du thread ayant appelé `LoadLibrary`.  Il n'appelle pas la fonction de point d'entrée si la DLL est déjà liée au processus, suite à un appel antérieur à `LoadLibrary` sans appel correspondant à la fonction `FreeLibrary`.  
  
 Pour les applications MFC qui chargent des DLL d'extension, nous recommandons d'utiliser `AfxLoadLibrary` à la place de `LoadLibrary`.  `AfxLoadLibrary` gère la synchronisation des threads avant l'appel de `LoadLibrary`.  L'interface \(prototype de fonction\) de `AfxLoadLibrary` est identique à celle de `LoadLibrary`.  
  
 Si Windows ne peut pas charger la DLL, le processus peut tenter de récupérer à partir de l'erreur.  Par exemple, il peut notifier l'erreur à l'utilisateur et lui demander de spécifier un autre chemin d'accès à la DLL.  
  
> [!IMPORTANT]
>  Si le code doit être exécuté sous Windows NT 4, Windows 2000 ou Windows XP \(version antérieure à SP1\), veillez à spécifier le chemin d'accès complet de toute DLL.  Sur ces systèmes d'exploitation, la recherche porte d'abord sur le répertoire actif lors du chargement des fichiers.  Si vous ne spécifiez pas le chemin d'accès au fichier, un fichier qui n'est pas celui que vous aviez prévu risque d'être chargé.  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière implicite](../build/linking-implicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Chemin de recherche utilisé par Windows pour rechercher une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary et AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)