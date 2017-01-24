---
title: "Listes d&#39;initialiseurs | Microsoft Docs"
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
  - "listes d'initialiseurs"
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Listes d&#39;initialiseurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les listes d'initialiseurs des constructeurs sont maintenant appelées avant le constructeur de la classe de base.  
  
## Remarques  
 Avant Visual C\+\+ 2005, le constructeur de classe de base était appelé avant la liste d'initialiseurs lors de la compilation avec les extensions managées pour C\+\+.  Maintenant, lors de la compilation avec **\/clr**, la liste d'initialiseurs est appelée en premier.  
  
## Voir aussi  
 [Modification d'ordre général apportée au langage](../dotnet/general-language-changes-cpp-cli.md)