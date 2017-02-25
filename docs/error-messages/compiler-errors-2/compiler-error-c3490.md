---
title: "Erreur du compilateur C3490 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3490"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3490"
ms.assetid: 7638559a-fd06-4527-a9c1-0c8ae68b3123
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3490
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de modifier 'var' car il est accessible via un objet const  
  
 Une expression lambda déclarée dans une méthode `const` ne peut pas modifier des données membres non mutables.  
  
### Pour corriger cette erreur  
  
-   Supprimez le modificateur `const` de votre déclaration de méthode.  
  
## Exemple  
 L’exemple suivant génère l’erreur C3490, car il modifie la variable membre`_i` dans une méthode `const` :  
  
```  
// C3490a.cpp // compile with: /c class C { void f() const  { auto x = [=]() { _i = 20; }; // C3490 } int _i; };  
```  
  
## Exemple  
 L’exemple suivant corrige l’erreur C3490 en supprimant le modificateur `const` de la déclaration de méthode :  
  
```  
// C3490b.cpp // compile with: /c class C { void f() { auto x = [=]() { _i = 20; }; } int _i; };  
```  
  
## Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)