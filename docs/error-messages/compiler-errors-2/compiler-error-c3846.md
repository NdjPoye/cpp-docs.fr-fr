---
title: Erreur du compilateur C3846 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 58ffd3f240505d173014f1f9b358b4957a41eaf5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3846"></a>Erreur du compilateur C3846
'symbole' : Impossible d’importer le symbole de 'assembly2' : car 'symbole' a déjà été importé à partir d’un autre assembly 'assembly1'  
  
 Un symbole n’a pas pu être importé à partir d’un assembly référencé, car il a été précédemment importé à partir d’un assembly référencé.  
  
## <a name="example"></a>Exemple
L’exemple suivant génère l’erreur C3846 :  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Et ensuite, compilez cela :  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  

