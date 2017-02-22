---
title: "Erreur du compilateur C2765 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2765"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2765"
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2765
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : une spécialisation explicite d'un modèle de fonction ne peut pas avoir d'argument par défaut  
  
 Les arguments par défaut ne sont pas autorisés sur une spécialisation explicite d'un modèle de fonction.  Pour plus d'informations, consultez [Spécialisation explicite de modèles de fonctions](../../cpp/explicit-specialization-of-function-templates.md).  
  
 L'exemple suivant génère l'erreur C2765 :  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```