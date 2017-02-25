---
title: "Erreur du compilateur C2990 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2990"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2990"
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur du compilateur C2990
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : le type sans classe a déjà été déclaré comme type de classe  
  
 La classe non générique ou de modèle redéfinit une classe générique ou de modèle.  Recherchez la présence d'un conflit dans les fichiers d'en\-tête.  
  
 L'exemple suivant génère l'erreur C2990 :  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 L'erreur C2990 peut également se produire lors de l'utilisation de génériques :  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 L'erreur C2990 peut également se produire en raison d'une modification avec rupture dans le compilateur Visual C\+\+ pour Visual C\+\+ 2005 ; ce dernier exige désormais que plusieurs déclarations d'un même type soient identiques en termes de spécification de modèle.  
  
 L'exemple suivant génère l'erreur C2990 :  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```