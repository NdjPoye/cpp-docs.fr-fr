---
title: "Erreur du compilateur C2070 | Microsoft Docs"
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
  - "C2070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2070"
ms.assetid: 4c8dea63-1227-4aba-be26-2462537f86fb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : opérande sizeof non conforme  
  
 L'opérateur [sizeof](../../cpp/sizeof-operator.md) requiert une expression ou un nom de type.  
  
 L'exemple suivant génère l'erreur C2070 :  
  
```  
// C2070.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(func);   // C2070  
}  
```  
  
 Résolution possible :  
  
```  
// C2070b.cpp  
void func() {}  
int main() {  
   int a;  
   a = sizeof(a);  
}  
```