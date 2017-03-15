---
title: Erreur du compilateur C2842 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: e4b3067b3293892d25dace565538a022e49a6f6f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2842"></a>Erreur du compilateur C2842
'classe' : un type managé ou WinRT ne peut pas définir son propre 'operator new' ou 'operator delete'  
  
 Vous pouvez définir vos propres **nouveau opérateur ou **opérateur delete ** pour gérer l’allocation de mémoire sur le tas natif. Toutefois, les classes de référence ne peuvent pas définir ces opérateurs car ils sont alloués seulement sur le tas managé.  

  
 Pour plus d’informations, consultez [les opérateurs définis par l’utilisateur (C + c++ / CLI)](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'erreur C2842.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  

