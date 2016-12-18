---
title: "Diff&#233;rences entre les applications et les DLL | Microsoft Docs"
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
  - "applications (C++), différences par rapport aux DLL"
  - "DLL (C++), différences par rapport aux applications"
  - "fichiers exécutables (C++), DLL (différences par rapport aux applications)"
ms.assetid: 8f271523-d8d0-4ad1-84d2-0c5645d7fd5b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Diff&#233;rences entre les applications et les DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si les DLL et les applications ont en commun d'être des modules de programme exécutables, elles diffèrent cependant par bien des aspects.  Pour l'utilisateur final, la différence la plus visible est que les DLL ne sont pas des programmes qui peuvent être exécutés directement.  Du point de vue du système, il existe deux différences fondamentales entre les applications et les DLL :  
  
-   Une application peut avoir plusieurs instances d'elle\-même qui s'exécutent simultanément sur le système, alors qu'une DLL ne peut avoir qu'une seule instance.  
  
-   Contrairement à une DLL, une application peut posséder des objets tels qu'une pile, une mémoire globale, des handles de fichiers et une file d'attente de messages.  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
-   [Lier un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Avantages de l'utilisation des DLL](../build/advantages-of-using-dlls.md)  
  
-   [DLL non\-MFC : vue d'ensemble](../build/non-mfc-dlls-overview.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension : vue d'ensemble](../build/extension-dlls-overview.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)