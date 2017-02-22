---
title: "Erreur du compilateur C2062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2062"
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type 'type' inattendu  
  
 Le compilateur n'attendait pas un nom de type.  
  
 L'exemple suivant génère l'erreur C2062 :  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 L'erreur C2062 peut également se produire en raison de la manière dont le compilateur gère les types indéfinis dans la liste de paramètres d'un constructeur.  Si le compilateur rencontre un type indéfini \(mal orthographié ?\), il suppose que le constructeur est une expression, et émet l'erreur C2062.  Pour résoudre ce problème, utilisez uniquement des types définis dans la liste de paramètres d'un constructeur.