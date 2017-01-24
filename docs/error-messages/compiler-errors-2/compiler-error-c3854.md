---
title: "Erreur du compilateur C3854 | Microsoft Docs"
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
  - "C3854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3854"
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'expression à gauche de '\=' correspond à une fonction.Assignation à une fonction impossible \(une fonction n'est pas une l\-value\)  
  
 Une référence ne peut pas être réinitialisée.  L'annulation d'une référence à une fonction donne une fonction, qui est une valeur rvalue, à laquelle l'assignation est impossible.  Par conséquent, vous ne pouvez pas assigner à une fonction par l'intermédiaire d'une référence.  
  
 L'exemple suivant génère l'erreur C3854 :  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```