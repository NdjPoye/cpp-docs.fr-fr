---
title: "&#201;tats du module d&#39;une DLL normale li&#233;e de mani&#232;re dynamique aux MFC | Microsoft Docs"
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
  - "DLL (C++), états des modules"
  - "DLL MFC (C++), DLL normales"
  - "états des modules (C++)"
  - "états des modules (C++), DLL normales liées dynamiquement aux"
  - "DLL normales (C++), liées dynamiquement à MFC"
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;tats du module d&#39;une DLL normale li&#233;e de mani&#232;re dynamique aux MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La possibilité de lier de manière dynamique une DLL normale à la DLL MFC permet quelques configurations qui sont très complexes.  Par exemple, une DLL normale et l'exécutable qui l'utilise peuvent tous deux être liés de manière dynamique à la DLL MFC et à toute DLL d'extension.  
  
 Cette configuration pose un problème en ce qui concerne les données globales MFC \(par exemple le pointeur désignant l'objet `CWinApp` en cours et les tables de handles\).  
  
 Avant la version 4.0 des MFC, ces données globales résidaient dans la DLL MFC elle\-même et étaient partagées par tous les modules du processus.  Comme chaque processus utilisant une DLL Win32 obtient sa propre copie des données des DLL, cette méthode fournissait un moyen aisé de suivre les données processus par processus.  En outre, comme le modèle AFXDLL supposait la présence d'un seul objet `CWinApp` et d'un seul jeu de tables de handles dans le processus, ces éléments pouvaient être suivis dans la DLL MFC proprement dite.  
  
 Mais avec la possibilité de lier de manière dynamique une DLL normale à la DLL MFC, il est maintenant acceptable d'avoir deux ou plusieurs objets `CWinApp` dans un processus — et également deux ou plusieurs jeux de tables de handles.  Comment la bibliothèque MFC assure\-t\-elle le suivi des éléments qu'elle doit utiliser ?  
  
 La solution consiste à remettre à chaque module \(application ou DLL normale\) sa propre copie de ces informations sur l'état global.  Ainsi, un appel à **AfxGetApp** dans la DLL normale retourne un pointeur désignant l'objet `CWinApp` dans la DLL, et non celui dans l'exécutable.  Cette copie par module des données globales des MFC est appelée « état du module » et est décrite dans [MFC Technical Note 58](../mfc/tn058-mfc-module-state-implementation.md).  
  
 La procédure de fenêtre commune des MFC bascule automatiquement vers l'état du module approprié, ce qui fait que vous n'avez pas besoin de vous en inquiéter dans les gestionnaires de messages éventuellement implémentés dans la DLL normale.  Mais quand l'exécutable appelle la DLL normale, vous devez définir de manière explicite l'état du module en cours en tant que celui de la DLL.  Pour ce faire, utilisez la macro **AFX\_MANAGE\_STATE** dans chaque fonction exportée à partir de la DLL.  Pour cela, ajoutez la ligne de code suivante au début des fonctions exportées à partir de la DLL :  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [DLL normales liées de manière dynamique aux MFC](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [DLL d'extension](../build/extension-dlls-overview.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)