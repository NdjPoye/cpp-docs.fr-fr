---
title: "Erreur du compilateur C2198 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2198"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2198"
ms.assetid: 638a845c-9d7f-4115-a9aa-d72455605668
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2198
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : pas assez d’arguments pour un appel  
  
 Le compilateur a détecté un nombre insuffisant de paramètres pour un appel à la fonction, ou une déclaration de fonction incorrecte.  
  
 L’exemple suivant génère l’erreur C2198 :  
  
```  
// C2198.c // compile with: /c void func( int, int ); int main() { func( 1 );   // C2198 only one actual parameter func( 1, 1 );   // OK }  
```