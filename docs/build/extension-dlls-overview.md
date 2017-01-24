---
title: "DLL d&#39;extension&#160;: vue d&#39;ensemble | Microsoft Docs"
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
  - "AFXDLL (bibliothèque)"
  - "DLL (C++), extension"
  - "DLL d'extension (C++), à propos des DLL d'extension"
  - "DLL MFC (C++), DLL d'extension"
  - "versions DLL partagées (C++)"
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL d&#39;extension&#160;: vue d&#39;ensemble
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une DLL d'extension des MFC est une DLL qui implémente généralement des classes réutilisables dérivées de classes de la bibliothèque MFC.  Les DLL d'extension sont générées à l'aide de la version bibliothèque de liens dynamiques des MFC \(appelée également version partagée des MFC\).  Seuls les exécutables MFC \(applications ou DLL normales\) qui sont générés à l'aide de la version partagée des MFC peuvent utiliser une DLL d'extension.  Avec une DLL d'extension, vous pouvez dériver de nouvelles classes personnalisées à partir des MFC puis offrir cette version étendue des MFC aux applications qui appellent votre DLL.  
  
 Les DLL d'extension peuvent également être utilisées pour passer des objets dérivés des MFC entre l'application et la DLL.  Les fonctions membres associées à l'objet passé existent dans le module où l'objet a été créé.  Comme ces fonctions sont exportées correctement lorsque vous utilisez la version DLL partagée de MFC, vous pouvez passer librement des pointeurs désignant des objets MFC ou dérivés des MFC entre une application et les DLL d'extension chargées par elle.  
  
 Pour obtenir un exemple de DLL répondant aux critères de base d'une DLL d'extension, consultez l'exemple MFC [DLLHUSK](http://msdn.microsoft.com/fr-fr/dfcaa6ff-b8e2-4efd-8100-ee3650071f90).  Examinez particulièrement les fichiers Testdll1.cpp et Testdll2.cpp.  
  
 Remarquez que le terme AFXDLL n'a plus cours dans la documentation Visual C\+\+.  Une DLL d'extension possède les mêmes caractéristiques que l'ancienne AFXDLL.  
  
## Que voulez\-vous faire ?  
  
-   [Initialiser une DLL d'extension](../build/initializing-extension-dlls.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [DLL d'extension](../build/extension-dlls.md)  
  
-   [Utilisation de DLL d'extension de type base de données, OLE et sockets dans des DLL normales](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [DLL non\-MFC : vue d'ensemble](../build/non-mfc-dlls-overview.md)  
  
-   [DLL normales liées de manière statique aux MFC](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Création d'une DLL MFC](../mfc/reference/mfc-dll-wizard.md)  
  
## Voir aussi  
 [Types de DLL](../build/kinds-of-dlls.md)