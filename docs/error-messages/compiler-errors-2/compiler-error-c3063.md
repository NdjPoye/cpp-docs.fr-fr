---
title: "Erreur du compilateur C3063 | Microsoft Docs"
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
  - "C3063"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3063"
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3063
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

opérateur 'opérateur' : tous les opérandes doivent avoir le même type énumération  
  
 Lors de l'utilisation d'opérateurs sur des énumérateurs, les deux opérandes doivent être de type énumération.  Pour plus d'informations, consultez [Utilisation d'opérateurs et d'énumérations](../../misc/operators-and-enumerations.md).  
  
 L'exemple suivant génère l'erreur C3063 :  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```