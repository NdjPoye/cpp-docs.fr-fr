---
title: "Erreur du compilateur C3072 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3072"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3072"
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3072
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'opérateur 'opérateur' ne peut pas être appliqué à une instance d'une classe ref  
  
 Utilisez l'opérateur '`operator`' unaire pour convertir une instance d'une classe ref en un type de handle  
  
 Un type CLR exige des opérateurs CLR, et non des opérateurs natifs \(ou standard\).  Pour plus d'informations, consultez [Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3072 :  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```