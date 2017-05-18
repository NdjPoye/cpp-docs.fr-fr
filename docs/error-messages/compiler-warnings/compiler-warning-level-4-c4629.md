---
title: Compilateur avertissement (niveau 4) C4629 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4629
dev_langs:
- C++
helpviewer_keywords:
- C4629
ms.assetid: 158cde12-bae5-4d43-b575-b52b35aaa0b9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d43d9be531611c40595d56a07f8a8a007cc2bf4b
ms.contentlocale: fr-fr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4629"></a>Avertissement du compilateur (niveau 4) C4629
digrammes utilisés, séquence de caractères 'digramme' interprétée comme jeton 'caractère' (insérez un espace entre les deux caractères si cela n’est pas ce que vous souhaitiez)  
  
 Sous [/Za](../../build/reference/za-ze-disable-language-extensions.md), le compilateur vous avertit lorsqu’il détecte un digramme.  
  
 L’exemple suivant génère l’avertissement C4629 :  
  
```  
// C4629.cpp  
// compile with: /Za /W4  
int main()  
<%   // C4629 <% digraph for {  
}  
```
