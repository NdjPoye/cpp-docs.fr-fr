---
title: "Technologie active et DLL | Microsoft Docs"
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
  - "technologie active (C++)"
  - "Automation (C++), DLL"
  - "DLL (C++), technologie active"
  - "DLL de serveur in-process"
  - "DLL MFC (C++), technologie active"
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Technologie active et DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La technologie active permet l'implémentation complète de serveurs d'objets dans une DLL.  Ce type de serveur est appelé serveur in\-process.  Les MFC ne prennent pas en charge complètement les serveurs in\-process pour toutes les fonctionnalités d'édition sur place, essentiellement parce que la technologie active ne permet pas à un serveur de se connecter à la boucle de messages principale du conteneur.  Les MFC requièrent un accès à la boucle de messages de l'application conteneur pour gérer les touches accélérateur et le traitement des temps d'inactivité.  
  
 Si vous écrivez un serveur Automation et que celui\-ci ne dispose pas d'une interface utilisateur, vous pouvez en faire un serveur in\-process et l'intégrer complètement dans une DLL.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Serveurs Automation](../mfc/automation-servers.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)