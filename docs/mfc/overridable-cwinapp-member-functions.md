---
title: "Fonctions membres CWinApp rempla&#231;ables | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application (classe)"
  - "CWinApp (classe), remplaçables"
  - "substituer, fonctions remplaçables dans CWinApp"
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Fonctions membres CWinApp rempla&#231;ables
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CWinApp](../mfc/reference/cwinapp-class.md) fournit plusieurs fonctions membres clés substituables \(`CWinApp` remplace les membres de la classe [CWinThread](../mfc/reference/cwinthread-class.md), à partir de laquelle `CWinApp` dérive\) :  
  
-   [InitInstance](../mfc/initinstance-member-function.md)  
  
-   [Run](../mfc/run-member-function.md)  
  
-   [ExitInstance](../mfc/exitinstance-member-function.md)  
  
-   [OnIdle](../mfc/onidle-member-function.md)  
  
 La seule fonction membre `CWinApp` que vous devez remplacer est `InitInstance`.  
  
## Voir aussi  
 [CWinApp : classe d'application](../mfc/cwinapp-the-application-class.md)