---
title: "Avertissement du compilateur (niveau 1) C4311 | Microsoft Docs"
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
  - "C4311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4311"
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : troncation de pointeur de 'type' à 'type'  
  
 Cet avertissement détecte les problèmes de troncation de pointeur 64 bits.  Par exemple, si le code est compilé pour une architecture 64 bits, la valeur d'un pointeur \(64 bits\) est tronquée si elle est affectée à un `int` \(32 bits\).  Pour plus d'informations, consultez [Règles d'utilisation des pointeurs](http://msdn.microsoft.com/library/windows/desktop/aa384242).  
  
 Pour plus d'informations sur les causes courantes de l'avertissement C4311, consultez [Erreurs courantes du compilateur](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 L'exemple de code suivant génère l'avertissement C4311 quand il est compilé pour une cible 64 bits, puis indique comment le corriger :  
  
```  
// C4311.cpp  
// compile by using: cl /W1 C4311.cpp  
int main() {  
   void* p = &p;  
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets  
   unsigned long long j = (unsigned long long) p;   // OK  
}  
  
```