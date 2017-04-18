---
title: Erreur du compilateur C2944 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2944
dev_langs:
- C++
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4da1b3731b8e984ccf14a3c106f86256fdbf4afb
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2944"></a>Erreur du compilateur C2944
'classe' : type-class-id redéfini comme argument de valeur d’un modèle  
  
 Vous ne pouvez pas utiliser une classe générique ou de modèle à la place d’un symbole comme argument de valeur de modèle.  
  
 L’exemple suivant génère l’erreur C2944 :  
  
```  
// C2944.cpp  
// compile with: /c  
template<class T>  
class TC { };   
  
template <int TC<int> > struct X1 { };   // C2944  
  
template <class T > struct X2 {};  
```  
  
 L’erreur C2944 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2944b.cpp  
// compile with: /clr /c  
generic<class T>  
ref class GC {};  
  
template <int GC<int> > struct X2 { };   // C2944  
template <class T> struct X3 {};   // OK  
```
