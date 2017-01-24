---
title: "Erreur du compilateur C2430 | Microsoft Docs"
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
  - "C2430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2430"
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

plus d'un registre d'index dans 'identificateur'  
  
 Plusieurs registres sont échelonnés.  Le compilateur prend en charge l'indexage échelonné, mais vous ne pouvez échelonner qu'un registre.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2430 :  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```