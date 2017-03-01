---
title: Erreur du compilateur C3622 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3622
dev_langs:
- C++
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
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
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ed81cc21e3c3ae574a0c83a692f75638d24111de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3622"></a>Erreur du compilateur C3622
'classe' : une classe déclarée comme 'mot clé' ne peut pas être instanciée.  
  
Une tentative d’instancier une classe marquée en tant que [abstraite](../../windows/abstract-cpp-component-extensions.md). Une classe marquée comme `abstract` peut être une classe de base, mais elle ne peut pas être instanciée.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère C3622.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  

