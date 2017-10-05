---
title: noinline | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noinline
- noinline_cpp
dev_langs:
- C++
helpviewer_keywords:
- noinline __declspec keyword
- __declspec keyword [C++], noinline
ms.assetid: f259d55b-dec7-4bde-8cf9-14521e4fdc42
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2ba1e7f6563b480cadc171bd6cea6e5fb4cb9839
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="noinline"></a>noinline
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 **__declspec (noinline)** indique au compilateur de ne jamais inline une fonction membre particulière (fonction dans une classe).  
  
 Il peut être préférable de ne pas incorporer une fonction si elle est petite et non essentielle pour les performances de votre code. Autrement dit, s'il s'agit d'une petite fonction et qu'il est probable qu'elle sera rarement appelée, comme par exemple une fonction qui gère une condition d'erreur.  
  
 Sachez que si une fonction est marquée `noinline`, la fonction appelante est plus petite et par conséquent elle-même un candidat pour l'incorporation par le compilateur.  
  
```  
class X {  
   __declspec(noinline) int mbrfunc() {  
      return 0;   
   }   // will not inline  
};  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [inline, __inline, \__forceinline](inline-functions-cpp.md)


