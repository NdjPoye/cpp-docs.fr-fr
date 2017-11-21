---
title: Erreur du compilateur C3637 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3637
dev_langs: C++
helpviewer_keywords: C3637
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 111e4025122ca298939e696901cb37f079d4be21
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3637"></a>Erreur du compilateur C3637
'fonction' : une définition de fonction friend ne peut pas être une spécialisation d’un type de fonction  
  
 Une fonction friend a été définie correctement pour un modèle ou un générique.  
  
 L’exemple suivant génère l’erreur C3637 :  
  
```  
// C3637.cpp  
template <class T>  
void f();  
  
struct S {  
   friend void f<int>() {}   // C3637  
};  
```  
  
 Résolution possible :  
  
```  
// C3637b.cpp  
// compile with: /c  
template <class T>  
void f();  
  
struct S {  
   friend void f() {}  
};  
```  
  
 L’erreur C3637 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C3637c.cpp  
// compile with: /clr  
  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf<int>() {}   // C3637  
};  
```  
  
 Résolution possible :  
  
```  
// C3637d.cpp  
// compile with: /clr /c  
generic <class T>  
void gf();  
  
struct S {  
   friend void gf() {}  
};  
```