---
title: "Erreur du compilateur C2390 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2390"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2390"
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2390
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : classe de stockage incorrecte 'spécificateur '  
  
 La classe de stockage n'est pas valide pour l'identificateur de portée globale.  La classe de stockage par défaut est utilisée à la place de la classe non valide.  
  
 Résolutions possibles :  
  
-   Si l'identificateur est une fonction, déclarez\-le à l'aide du stockage `extern`.  
  
-   Si l'identificateur est un paramètre formel ou une variable locale, déclarez\-le à l'aide du stockage automatique.  
  
-   Si l'identificateur est une variable globale, déclarez\-le sans classe de stockage \(stockage automatique\).  
  
## Exemple  
  
-   L'exemple suivant génère l'erreur C2390 :  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```