---
title: "Erreur du compilateur C2702 | Microsoft Docs"
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
  - "C2702"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2702"
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2702
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_except ne peut pas apparaître dans un bloc de fin  
  
 Un gestionnaire d'exceptions \(`__try`\/`__except`\) ne peut pas être imbriqué dans un bloc `__finally`.  
  
 L'exemple suivant génère l'erreur C2702 :  
  
```  
// C2702.cpp  
// processor: x86 IPF  
int Counter;  
int main() {  
   __try {}  
   __finally {  
      __try {}   // C2702  
      __except( Counter ) {}   // C2702  
   }  
}  
```