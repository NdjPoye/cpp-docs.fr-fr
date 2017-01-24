---
title: "Erreur du compilateur C3535 | Microsoft Docs"
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
  - "C3535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3535"
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de déduire le type pour « type1 » à partir de « type2 »  
  
 Le type de la variable déclarée par le mot clé `auto` ne peut pas être déduit du type de l'expression d'initialisation.  Par exemple, cette erreur se produit si l'expression d'initialisation a la valeur `void`, ce qui n'est pas un type.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que le type de l'expression d'initialisation n'est pas `void`.  
  
2.  Vérifiez que la déclaration n'est pas un pointeur vers un type fondamental.  Pour plus d'informations, consultez [Types fondamentaux](../../cpp/fundamental-types-cpp.md).  
  
3.  Vérifiez que si la déclaration est un pointeur vers un type, l'expression d'initialisation est un type pointeur.  
  
## Exemple  
 L'exemple suivant donne C3535 parce que l'expression d'initialisation a la valeur `void`.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## Exemple  
 L'exemple suivant donne C3535 parce que l'instruction déclare la variable `x` comme un pointeur vers un type déduit, mais le type de l'expression d'initialiseur est double.  Par conséquent, le compilateur ne peut pas déduire le type de la variable.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## Exemple  
 L'exemple suivant donne C3535 parce que la variable `p` déclare un pointeur vers un type déduit, mais l'expression d'initialisation n'est pas un type pointeur.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)   
 [Types fondamentaux](../../cpp/fundamental-types-cpp.md)