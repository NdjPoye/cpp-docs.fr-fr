---
title: "Isolement de la biblioth&#232;que de contr&#244;les communs MFC | Microsoft Docs"
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
  - "MFC, Common Controls (bibliothèque)"
ms.assetid: 7471e6f0-49b0-47f7-86e7-8d6bc3541694
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Isolement de la biblioth&#232;que de contr&#244;les communs MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque de contrôles communs est maintenant détachée de MFC, ce qui permet à différents modules \(tels que les DLL utilisateur\) d'utiliser des versions différentes de la bibliothèque de contrôles communs en spécifiant la version dans les manifestes.  
  
 Une application MFC \(ou le code utilisateur appelée par MFC\) effectue des appels aux API de bibliothèque de contrôles communs grâce à des fonctions wrapper nommées `Afx`*FunctionName*, où *FunctionName* est le nom d'une API de contrôles communs.  Ces fonctions wrappers sont définies dans afxcomctl32.h et afxcomctl32.inl.  
  
 Vous pouvez utiliser les macros [AFX\_COMCTL32\_IF\_EXISTS](../Topic/AFX_COMCTL32_IF_EXISTS.md) et [AFX\_COMCTL32\_IF\_EXISTS2](../Topic/AFX_COMCTL32_IF_EXISTS2.md) \(définies dans afxcomctl32.h\) pour déterminer si la bibliothèque de contrôles communs implémente certaines API au lieu d'appeler [GetProcAddress](../build/getprocaddress.md).  
  
 Techniquement, vous effectuez des appels aux API de bibliothèque de contrôles communs à travers une classe wrapper, `CComCtlWrapper` \(défini dans afxcomctl32.h\).  `CComCtlWrapper` est également responsable du chargement et de déchargement de comctl32.dll.  L'état du module de MFC contient un pointeur vers une instance de `CComCtlWrapper`.  Vous pouvez accéder à la classe wrapper à l'aide de la macro `afxComCtlWrapper`.  
  
 Notez que l'appel direct à l'API de contrôles communs \(sans utilisation des fonctions wrapper MFC\) d'une application MFC ou une DLL utilisateur s'exécutera dans la plupart des cas, car l'application MFC ou la DLL utilisateur est liée à la bibliothèque de contrôles communs demandée dans le manifeste\).  Toutefois, le code MFC lui\-même doit utiliser les wrappers, car le code MFC peut être appelé depuis des DLL utilisateur avec différentes versions de bibliothèque de contrôles communs.