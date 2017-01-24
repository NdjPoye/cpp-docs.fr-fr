---
title: "Erreur du compilateur C3532 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3532"
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : utilisation incorrecte de « auto »  
  
 Le type indiqué ne peut pas être déclaré avec le mot clé `auto`.  Par exemple, vous ne pouvez pas utiliser le mot clé `auto` pour déclarer un tableau ou un type de retour de méthode.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que l'expression d'initialisation donne un type valide.  
  
2.  Vérifiez que vous ne déclarez pas un tableau ou un type de retour de méthode.  
  
## Exemple  
 L'exemple suivant donne C3532 parce que le mot clé `auto` ne peut pas déclarer un type de retour de méthode.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## Exemple  
 L'exemple suivant donne C3532 parce que le mot clé `auto` ne peut pas déclarer de tableau.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)