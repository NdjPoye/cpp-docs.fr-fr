---
title: "Erreur du compilateur C3704 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3704"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3704"
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3704
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : une méthode vararg ne peut pas déclencher d'événements  
  
 Vous avez essayé d'utiliser un [\_\_event](../../cpp/event.md) sur une méthode vararg.  Pour remédier à cette erreur, remplacez l'appel `fireEvent(int i, ...)` par l'appel `fireEvent(int i)` comme illustré dans l'exemple de code suivant.  
  
 L'exemple suivant génère l'erreur C3704 :  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```