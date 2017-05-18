---
title: Compilateur avertissement (niveau 4) C4295 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: 5
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: b831b8e7b838ef25679d49a132c66d4b378fdcd7
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4295"></a>Avertissement du compilateur (niveau 4) C4295
  
> '*tableau*' : tableau est trop petit pour comporter un caractère null de fin  
  
 Un tableau a été initialisé, mais le dernier caractère dans le tableau n’est pas une valeur null ; accès au tableau peut produire des résultats inattendus.  
  
## <a name="example"></a>Exemple  
  
 L’exemple suivant génère l’erreur C4295. Pour résoudre ce problème, vous pouvez déclarer la taille du tableau plus volumineux pour contenir une de fin null à partir de l’initialiseur.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```
