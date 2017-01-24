---
title: "Erreur du compilateur C2555 | Microsoft Docs"
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
  - "C2555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2555"
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe1::fonction1' : le type de retour de la fonction virtuelle de substitution diffère de 'classe2::fonction2' et n'est pas covariant  
  
 Une fonction virtuelle et une fonction de substitution dérivée ont des listes de paramètres identiques mais des types de retour différents.  Une fonction de substitution d'une classe dérivée ne peut pas différer d'une fonction virtuelle d'une classe de base que par son type de retour.  
  
 Pour corriger cette erreur, effectuer le cast de la valeur de retour après l'appel de la fonction virtuelle.  
  
 Cette erreur peut également être générée si vous compilez avec \/clr.   Par exemple, l'équivalent C\+\+ de la déclaration C\# suivante :  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 est  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Pour plus d'informations sur l'erreur C2555, consultez l'article Q240862 de la Base de Connaissances.  
  
 L'exemple suivant génère l'erreur C2555 :  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```