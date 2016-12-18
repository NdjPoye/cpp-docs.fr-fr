---
title: "Erreur du compilateur C3744 | Microsoft Docs"
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
  - "C3744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3744"
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_unhook doit avoir au moins 3 arguments pour les événements managés  
  
 La fonction [\_\_unhook](../../cpp/unhook.md) doit prendre trois paramètres lorsqu'elle est utilisée dans un programme qui est compilé pour les extensions managées pour C\+\+.  
  
 `__hook` et `__unhook` ne sont pas compatibles avec la programmation \/clr.  Utilisez plutôt les opérateurs \+\= et \-\=.  
  
 L'erreur C3744 n'est accessible qu'à l'aide de **\/clr:oldSyntax**.  
  
 L'exemple suivant génère l'erreur C3744 :  
  
```  
// C3744.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __delegate void delegate1();  
  
[ event_source(managed) ]  
public __gc class CPSource {  
public:  
   __event delegate1* event1;  
};  
  
[event_receiver(managed)]  
public __gc class CReceiver {  
public:  
   void Handler1() {  
   }  
  
   void UnhookAll1(CPSource* pSrc, CReceiver* pRec) {  
      pRec;  
      __unhook(pSrc);   // C3744  
      // The following line resolves the error.  
      // __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1);  
   }  
};  
  
int main() {  
}  
```