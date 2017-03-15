---
title: "Erreur du compilateur C2432 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2432"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2432"
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2432
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

référence non conforme à des données 16 bits dans 'identificateur'  
  
 Un registre 16 bits est utilisé comme registre d'index ou registre de base.  Le compilateur ne prend pas en charge le référencement des données 16 bits. Les registres 16 bits ne peuvent être utilisés comme registres de base ou d'index lors de la compilation du code 32 bits.  
  
 L'exemple suivant génère l'erreur C2432 :  
  
```  
// C2432.cpp  
// processor: x86  
int main() {  
   _asm mov eax, DWORD PTR [bx]   // C2432  
}  
```