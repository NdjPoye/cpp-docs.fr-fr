---
title: "Erreur du compilateur C2431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2431"
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C2431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

registre d'index non conforme dans 'identificateur'  
  
 Le registre ESP est échelonné ou utilisé à la fois comme registre de base et registre d'index.  L'encodage SIB du processeur x86 n'autorise ni l'un ni l'autre.  
  
 L'exemple suivant génère l'erreur C2431 :  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```