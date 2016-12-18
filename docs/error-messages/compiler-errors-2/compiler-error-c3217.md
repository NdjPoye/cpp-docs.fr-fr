---
title: "Erreur du compilateur C3217 | Microsoft Docs"
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
  - "C3217"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3217"
ms.assetid: 99070417-c23a-4d82-bdd2-04be1a07adea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3217
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'param' : le paramètre générique ne peut pas être limité dans cette déclaration  
  
 Une contrainte était mal formée ; le paramètre générique de la contrainte doit s’accorder avec le paramètre de modèle de classe générique.  
  
 L’exemple suivant génère l’erreur C3217 :  
  
```  
// C3217.cpp // compile with: /clr interface struct A {}; generic <class T> ref class C { generic <class T1> where T : A   // C3217 void f(); };  
```  
  
 L’exemple suivant illustre une résolution possible :  
  
```  
// C3217b.cpp // compile with: /clr /c interface struct A {}; generic <class T> ref class C { generic <class T1> where T1 : A void f(); };  
```