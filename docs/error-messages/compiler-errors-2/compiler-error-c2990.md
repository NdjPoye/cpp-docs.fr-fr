---
title: Erreur du compilateur C2990 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9a2433bec7992c73fb7e9b7f358e89b7e75da384
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2990"></a>Erreur du compilateur C2990
'classe' : type sans classe déjà été déclaré comme type de classe  
  
 Non générique ou la classe de modèle redéfinit une classe générique ou de modèle. Vérifiez les fichiers d’en-tête pour déterminer les conflits.  
  
 L’exemple suivant génère l’erreur C2990 :  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 L’erreur C2990 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 L’erreur C2990 peut également se produire en raison d’une modification avec rupture dans le compilateur Visual C++ pour Visual C++ 2005 ; le compilateur requiert désormais que plusieurs déclarations pour le même type soient identiques en ce qui concerne la spécification du modèle.  
  
 L’exemple suivant génère l’erreur C2990 :  
  
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
