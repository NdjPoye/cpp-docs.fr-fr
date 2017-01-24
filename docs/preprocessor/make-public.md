---
title: "make_public | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.make_public"
  - "make_public_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "make_public (pragma)"
  - "pragmas, make_public"
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# make_public
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique qu'un type natif doit disposer d'une accessibilité d'assembly public.  
  
## Syntaxe  
  
```  
#pragma make_public(type)  
```  
  
#### Paramètres  
 `type` est le nom du type que vous souhaitez pour disposer d'une accessibilité d'assembly public.  
  
## Notes  
 `make_public` est utile lorsque le type natif que vous souhaitez référencer provient d'un fichier .h que vous ne pouvez pas modifier.  Si vous souhaitez utiliser le type natif dans la signature d'une fonction publique dans un type disposant d'une visibilité d'assembly public, le type natif doit également avoir une accessibilité d'assembly public, sinon le compilateur émet un avertissement.  
  
 `make_public` doit être spécifiée au niveau de la portée globale et n'entre en vigueur qu'à partir du point auquel elle est déclarée à la fin du fichier de code source.  
  
 Le type natif peut être implicitement ou explicitement privé ; pour plus d'informations, consultez [Visibilité du type](../misc/type-visibility.md).  
  
## Exemple  
 L'exemple suivant est le contenu d'un fichier .h qui contient les définitions de deux structures natives.  
  
```  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## Exemple  
 L'exemple de code suivant utilise le fichier d'en\-tête et indique qu'à moins de marquer explicitement les structures natives comme publiques via `make_public`, le compilateur génère un avertissement lorsque vous tentez d'utiliser les structures natives dans la signature de la fonction publique dans un type managé public.  
  
```  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)