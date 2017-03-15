---
title: "Liaison d&#39;un ex&#233;cutable &#224; une DLL | Microsoft Docs"
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
  - "DLL (C++), lier"
  - "liaison de charge dynamique (C++)"
  - "fichiers exécutables (C++), lier à des DLL"
  - "liaison explicite (C++)"
  - "liaison implicite (C++)"
  - "liaison (C++), DLL"
  - "charger des DLL (C++)"
  - "runtime (C++), lier"
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Liaison d&#39;un ex&#233;cutable &#224; une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un fichier exécutable peut être lié à une DLL \(ou la charger\) selon l'une des deux méthodes suivantes :  
  
-   [Liaison implicite](../build/linking-implicitly.md)  
  
-   [Liaison explicite](../build/linking-explicitly.md)  
  
 La liaison implicite est parfois qualifiée de chargement statique ou liaison dynamique au moment du chargement.  La liaison explicite est parfois désignée par chargement dynamique ou liaison dynamique au moment de l'exécution.  
  
 Avec la liaison implicite, l'exécutable qui utilise la DLL est lié à une bibliothèque d'importation \(fichier .lib\) fournie par l'auteur de la DLL.  Le système d'exploitation charge la DLL en même temps que l'exécutable l'utilisant.  L'exécutable client appelle les fonctions exportées de la DLL comme si ces fonctions étaient contenues dans l'exécutable.  
  
 Avec la liaison explicite, l'exécutable utilisant la DLL doit effectuer des appels de fonctions de manière à charger et à décharger explicitement la DLL, ainsi que pour accéder aux fonctions exportées de la DLL.  L'exécutable client doit appeler les fonctions exportées par l'intermédiaire d'un pointeur de fonction.  
  
 Un exécutable peut utiliser la même DLL en ayant recours à l'une ou l'autre méthode de liaison.  De plus, ces mécanismes ne s'excluent pas mutuellement dans la mesure où un exécutable peut être lié de manière implicite à une DLL et un autre peut s'y attacher de manière explicite.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de bibliothèques d'importation et de fichiers d'exportation](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
-   [Chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)