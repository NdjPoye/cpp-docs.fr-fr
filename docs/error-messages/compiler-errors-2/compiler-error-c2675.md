---
title: "Erreur du compilateur C2675 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2675"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2675"
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Erreur du compilateur C2675
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

opérateur' unaire : 'type' ne définit pas cet opérateur ou une conversion vers un type acceptable pour l'opérateur prédéfini  
  
 L'erreur C2675 peut également se produire si vous utilisez un opérateur unaire et si le type ne définit pas l'opérateur ou une conversion vers un type acceptable pour l'opérateur prédéfini.  Pour utiliser l'opérateur, vous devez le surcharger pour le type spécifié ou définir une conversion vers un type pour lequel l'opérateur est défini.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2675 :  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```