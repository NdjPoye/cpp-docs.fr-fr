---
title: "Erreur du compilateur C2906 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2906"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2906"
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2906
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécialisation' : une spécialisation explicite requiert 'template \<\>'  
  
 Vous devez utiliser la nouvelle syntaxe pour une spécialisation explicite de modèles.  
  
 L'exemple suivant génère l'erreur C2906 :  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```