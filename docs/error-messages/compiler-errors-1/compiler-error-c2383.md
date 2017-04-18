---
title: Erreur du compilateur C2383 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2383
dev_langs:
- C++
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: faa2aa2c29ea34009f0812a3796d450a6877ca48
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2383"></a>Erreur du compilateur C2383
'*symbole*' : les arguments par défaut ne sont pas autorisés sur ce symbole  
  
 Le compilateur C++ n’autorise pas les arguments par défaut sur les pointeurs vers des fonctions.  
  
 Ce code a été accepté par le compilateur Visual C++ dans les versions antérieures de Visual Studio 2005, mais génère maintenant une erreur. Pour le code qui fonctionne dans toutes les versions de Visual C++, n’assignez pas de valeur par défaut à un argument de pointeur de fonction.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C2383 et illustre une solution possible :  
  
```cpp  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```
