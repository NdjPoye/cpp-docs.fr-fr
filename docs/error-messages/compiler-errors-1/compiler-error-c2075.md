---
title: "Erreur du compilateur&#160;C2075 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2075"
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur&#160;C2075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l’initialisation d’un tableau nécessite des accolades  
  
 Il n’y a aucune accolade autour de l’initialiseur de tableau spécifié.  
  
 L’exemple suivant génère l’erreur C2075 :  
  
```  
// C2075.c int main() { int i[] = 1, 2, 3 };   // C2075 }  
```  
  
 Résolution possible :  
  
```  
// C2075b.c int main() { int j[] = { 1, 2, 3 }; }  
```