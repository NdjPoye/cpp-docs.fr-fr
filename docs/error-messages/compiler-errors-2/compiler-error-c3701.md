---
title: "Erreur du compilateur C3701 | Microsoft Docs"
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
  - "C3701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3701"
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : source\_événement n'a pas d'événements  
  
 Vous avez essayé d'utiliser [event\_source](../../windows/event-source.md) sur une classe qui ne possède pas de méthodes d'événement.  Pour corriger cette erreur, ajoutez un ou plusieurs événements à la classe.  
  
 L'exemple suivant génère l'erreur C3701 :  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```