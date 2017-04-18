---
title: Compilateur avertissement (niveau 1) C4912 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4912
dev_langs:
- C++
helpviewer_keywords:
- C4912
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
caps.latest.revision: 6
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
ms.openlocfilehash: f98deb3ff941df35a68589142239404928d58d4c
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4912"></a>Avertissement du compilateur (niveau 1) C4912
'attribute' : comportement indéfini de l’attribut sur un UDT imbriqué  
  
 Les attributs qui s’appliquent aux UDT imbriqués (type défini par l’utilisateur : typedef, union ou struct) peuvent être ignorés.  
  
 Le code suivant montre comment cet avertissement est généré :  
  
```  
// C4912.cpp  
// compile with: /W1  
#include <windows.h>  
[emitidl, module(name="xx")];  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMy  
{  
};  
  
[coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")]  
class CMy : public IMy  
{  
   [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912  
};  
int main()  
{  
}  
```
