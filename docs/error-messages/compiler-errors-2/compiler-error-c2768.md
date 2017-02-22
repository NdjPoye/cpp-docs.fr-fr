---
title: "Erreur du compilateur C2768 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2768"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2768"
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2768
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : utilisation non conforme d'arguments template explicites  
  
 Le compilateur n'a pas pu déterminer si une définition de fonction devait être une spécialisation explicite d'un modèle de fonction ou si la définition de fonction devait être une nouvelle fonction.  
  
 Cette erreur a été introduite dans Visual Studio .NET 2003, avec les améliorations de conformité du compilateur.  
  
 L'exemple suivant génère l'erreur C2768 :  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```