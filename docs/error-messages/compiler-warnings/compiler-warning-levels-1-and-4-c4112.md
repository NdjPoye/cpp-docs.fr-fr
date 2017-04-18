---
title: Compilateur avertissement (niveaux 1 et 4) C4112 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 10
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
ms.openlocfilehash: 8a2c08b6c4bc8e1f2cf20e0236f76b5cd3020de4
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Avertissement du compilateur (niveaux 1 et 4) C4112
\#ligne nécessite un entier compris entre 1 et nombre  
  
 Le [#line](../../preprocessor/hash-line-directive-c-cpp.md) directive spécifie un paramètre entier qui est en dehors de la plage autorisée.  
  
 Si le paramètre spécifié est inférieur à 1, le compteur de lignes est réinitialisé à 1. Si le paramètre spécifié est supérieur à *nombre*, qui est la limite définie par le compilateur, le compteur de lignes est inchangé. Il s’agit d’un avertissement de niveau 1 sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement de niveau 4 avec les extensions Microsoft ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 L’exemple suivant génère l’avertissement C4112 :  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```
