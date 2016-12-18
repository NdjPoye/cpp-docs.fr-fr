---
title: "Erreur du compilateur C3206 | Microsoft Docs"
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
  - "C3206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3206"
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : argument type non valide pour 'param', liste d’arguments type absente dans le type de classe 'nom\_type'  
  
 Une fonction avec modèle est définie comme prenant un argument de type de modèle. Toutefois, un argument de type de modèle a été passé.  
  
 L’exemple suivant génère l’erreur C3206 :  
  
```  
// C3206.cpp template <class T> void f() {} template <class T> struct S {}; void f1() { f<S>();   // C3206 // try the following line instead // f<S<int> >(); }  
```  
  
 Solution possible :  
  
```  
// C3206b.cpp // compile with: /c template <class T> void f() {} template <class T> struct S {}; void f1() { f<S<int> >(); }  
```  
  
 L’erreur C3206 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C3206c.cpp // compile with: /clr generic <class GT1> void gf() {} generic <class T> value struct GS {}; int main() { gf<GS>();   // C3206 }  
```  
  
 Solution possible :  
  
```  
// C3206d.cpp // compile with: /clr generic <class GT1> void gf() {} generic <class T> value struct GS {}; int main() { gf<GS<int> >(); }  
```  
  
 Cette erreur peut également être générée en raison du travail de mise en conformité du compilateur pour Visual C\+\+ .NET 2003, où les modèles de classe ne sont pas autorisés comme argument de type de modèle.  
  
 Un modèle de classe n’est pas autorisé comme argument de type de modèle. Cela fonctionnait dans Visual C\+\+ .NET 2003, mais ce n’est pas valide en C\+\+.  
  
 La compilation de l’exemple suivant réussit dans Visual C\+\+ .NET 2002, mais échoue dans Visual C\+\+ .NET 2003 :  
  
```  
// C3206e.cpp template <class T> struct S {}; template <class T> void func() {   // takes a type T<int> t; } int main() { func<S>();   // C3206 S is not a type. }  
```  
  
 Solution possible :  
  
```  
// C3206f.cpp template <class T> struct S {}; template <class T> void func() {   // takes a type T t; } int main() { func<S<int> >(); }  
```  
  
 Si un paramètre de modèle est nécessaire, la résolution de l’erreur qui est valide à la fois dans les versions Visual C\+\+ .NET 2002 et Visual C\+\+ .NET 2003 exige que vous enveloppiez la fonction dans une classe de modèle qui prend un paramètre de modèle :  
  
```  
// C3206g.cpp template <class T> struct S {}; template<template<class> class TT> struct X { static void func() { TT<int> t1; TT<char> t2; } }; int main() { X<S>::func(); }  
```