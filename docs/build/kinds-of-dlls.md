---
title: "Types de DLL | Microsoft Docs"
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
  - "DLL (C++), MFC"
  - "DLL (C++), types"
  - "DLL MFC (C++), types"
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Types de DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique contient des informations destinées à vous aider à déterminer le type de DLL à générer.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> Différents types de DLL disponibles  
 Visual C\+\+ permet de générer des DLL Win32 en C ou C\+\+ qui ne font pas appel à la bibliothèque MFC \(Microsoft Foundation Class\).  Vous pouvez créer un projet de DLL non\-MFC à l'aide de l'Assistant Application Win32.  
  
 La bibliothèque MFC elle\-même est disponible, soit dans les bibliothèques de liaisons statiques soit dans un certain nombre de DLL, avec l'Assistant DLL MFC.  Si votre DLL utilise les MFC, Visual C\+\+ prend en charge trois scénarios différents de développement de DLL :  
  
-   Génération d'une DLL normale liée de manière statique aux MFC  
  
-   Génération d'une DLL normale liée de manière dynamique aux MFC  
  
-   Génération d'une DLL d'extension MFC qui est toujours liée de manière dynamique aux MFC  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DLL non\-MFC : vue d'ensemble](../build/non-mfc-dlls-overview.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension : vue d'ensemble](../build/extension-dlls-overview.md)  
  
-   [Type de DLL à utiliser](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a> Type de DLL à utiliser  
 Si la DLL ne fait pas intervenir les MFC, utilisez Visual C\+\+ pour générer une DLL Win32 non\-MFC.  La liaison de la DLL aux MFC \(de manière statique ou dynamique\) mobilise d'importantes ressources en termes de mémoire et d'espace disque.  Vous ne devez procéder à une liaison avec les MFC que si la DLL les utilise réellement.  
  
 Si la DLL est destinée à utiliser les MFC, et à être utilisée par des applications MFC ou non\-MFC, vous devez générer une DLL normale liée de manière dynamique aux MFC ou une DLL normale liée de manière statique aux MFC.  Dans la plupart des cas, vous souhaiterez probablement utiliser une DLL normale liée de manière dynamique aux MFC, car la taille du fichier de la DLL sera plus petite et l'économie réalisée au niveau des ressources mémoire peut être importante compte tenu de l'utilisation de la version partagée des MFC.  Si vous optez pour une version liée de manière statique aux MFC, la taille du fichier de la DLL sera plus grande et occupera vraisemblablement une portion supplémentaire de la mémoire car elle chargera sa propre copie privée du code de la bibliothèque MFC.  
  
 Il est plus rapide de générer une DLL liée de manière dynamique aux MFC qu'une DLL liée de manière statique aux MFC car il n'est pas nécessaire de lier les classes de la bibliothèque MFC à elles\-mêmes.  Ceci est particulièrement vrai dans les versions Debug où l'éditeur de liens doit compacter les informations de débogage.  En établissant une liaison avec une DLL qui contient déjà des informations de débogage, il y a moins d'informations de débogage à compacter dans la DLL.  
  
 L'un des inconvénients de la liaison dynamique avec les MFC est que vous devez distribuer les DLL partagées Mfcx0.dll et Msvcrxx.dll \(ou des fichiers similaires\) avec votre DLL.  Les DLL MFC peuvent être redistribuées librement, mais vous devez toujours installer les DLL dans le programme d'installation.  De plus, vous devrez livrer Msvcrxx.dll, qui contient la bibliothèque Runtime C, laquelle est utilisée à la fois par votre programme et les DLL MFC elles\-mêmes.  
  
 Si la DLL est destinée à être utilisée par des exécutables MFC, vous avez le choix entre générer une DLL normale et générer une DLL d'extension.  Si la DLL implémente des classes réutilisables dérivées de classes MFC existantes, ou si vous avez besoin de passer des objets dérivés des MFC entre l'application et la DLL, vous devez alors générer une DLL d'extension.  
  
 Si la DLL est liée de manière dynamique aux MFC, les DLL MFC peuvent être redistribuées avec la DLL.  Cette architecture est particulièrement utile pour le partage de la bibliothèque de classes entre plusieurs fichiers exécutables afin d'économiser l'espace disque et de réduire l'utilisation de la mémoire.  
  
 Avant la version 4.0, Visual C\+\+ ne prenait en charge que deux types de DLL fondés sur les MFC : USRDLL et AFXDLL.  Une DLL normale liée de manière statique aux MFC possède les mêmes caractéristiques que l'ancienne USRDLL.  Les DLL d'extension MFC possèdent les mêmes caractéristiques que l'ancienne AFXDLL.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DLL non\-MFC : vue d'ensemble](../build/non-mfc-dlls-overview.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension : vue d'ensemble](../build/extension-dlls-overview.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)