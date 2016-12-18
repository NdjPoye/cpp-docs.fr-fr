---
title: "Erreur du compilateur C3230 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3230"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3230"
ms.assetid: 5ec53f25-59f6-4801-81e7-7b68bf04994d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3230
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : l’argument de type de modèle de 'modèle' ne peut pas contenir de paramètre de type générique : 'paramètre'  
  
 Les modèles sont instanciés au moment de la compilation, mais les génériques sont instanciés au moment de l’exécution. Ainsi, il n’est pas possible de générer du code générique pouvant appeler le modèle, car celui\-ci ne peut pas être instancié au moment de l’exécution quand le type générique est enfin connu.  
  
 L’exemple suivant génère l’erreur C3230 :  
  
```  
// C3230.cpp // compile with: /clr /LD template <class S> void f(S t); generic <class U> ref class C { void f1(U x) { f(x);   // C3230 } };  
```