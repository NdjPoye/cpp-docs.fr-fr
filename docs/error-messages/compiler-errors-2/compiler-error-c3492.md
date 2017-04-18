---
title: Erreur du compilateur C3492 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3492
dev_langs:
- C++
helpviewer_keywords:
- C3492
ms.assetid: b1dc6342-9133-4b1f-a9c3-e8c65d20d121
caps.latest.revision: 7
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
ms.openlocfilehash: ff183b8a5171bc3849c4e8dd132dce6d75323f4e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3492"></a>Erreur du compilateur C3492
'var' : vous ne pouvez pas capturer un membre d’union anonyme  
  
 Vous ne pouvez pas capturer un membre d’une union sans nom.  
  
### <a name="to-correct-this-error"></a>Pour corriger cette erreur  
  
-   Donnez un nom à l’union et passez la structure d’union complète à la liste de capture de l’expression lambda.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3492, car il capture un membre d’une union anonyme :  
  
```  
// C3492a.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   };  
  
   ch = 'y';  
   [&x](char ch) { x = ch; }(ch); // C3492  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant résout l’erreur C3492 en nommant l’union et en passant la structure d’union complète à la liste de capture de l’expression lambda :  
  
```  
// C3492b.cpp  
  
int main()  
{  
   union  
   {  
      char ch;  
      int x;  
   } u;  
  
   u.ch = 'y';  
   [&u](char ch) { u.x = ch; }(u.ch);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions lambda](../../cpp/lambda-expressions-in-cpp.md)
