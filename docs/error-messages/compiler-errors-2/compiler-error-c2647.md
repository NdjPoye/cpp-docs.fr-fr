---
title: "Erreur du compilateur C2647 | Microsoft Docs"
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
  - "C2647"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2647"
ms.assetid: 1034589e-bc3e-41a6-831f-2a1a4b8a2500
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2647
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : impossible de déréférencer un 'type1' sur un 'type2'  
  
 L'opérande de gauche d'un opérateur pointeur vers membre \(`->*` ou `.*`\) ne peut pas être implicitement converti en un type se rapportant à l'opérateur de droite.  
  
 L'exemple suivant génère l'erreur C2647 :  
  
```  
// C2647.cpp  
class C {};  
class D {};  
  
int main() {  
   D d, *pd;  
   C c, *pc = 0;  
   int C::*pmc = 0;  
   pd->*pmc = 0;   // C2647  
   d.*pmc = 0;   // C2647  
  
   // OK  
   pc->*pmc = 0;  
   c.*pmc = 0;  
}  
```