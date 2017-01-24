---
title: "Erreur du compilateur C3493 | Microsoft Docs"
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
  - "C3493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3493"
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Impossible de capturer implicitement 'var', car aucun mode de capture par défaut n’a été spécifié  
  
 La capture de l’expression lambda vide, `[]`, spécifie que l’expression lambda ne capture pas de variables explicitement ou implicitement.  
  
### Pour corriger cette erreur  
  
-   Spécifiez un mode de capture par défaut, ou  
  
-   Capturez explicitement une ou plusieurs variables.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3493 parce qu’il modifie une variable externe, alors qu’il spécifie la clause de capture vide :  
  
```  
// C3493a.cpp int main() { int m = 55; [](int n) { m = n; }(99); // C3493 }  
```  
  
## Exemple  
 L’exemple suivant corrige C3493 en spécifiant la capture par référence comme mode de capture par défaut.  
  
```  
// C3493b.cpp int main() { int m = 55; [&](int n) { m = n; }(99); }  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)