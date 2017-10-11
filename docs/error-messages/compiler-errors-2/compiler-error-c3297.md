---
title: Erreur du compilateur C3297 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3297
dev_langs:
- C++
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2190bb4f2fe5c6195221deebe5b24097b614691
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3297"></a>Erreur du compilateur C3297
'constraint_2' : impossible d’utiliser 'constraint_1' en tant que contrainte, car 'constraint_1' a la contrainte de valeur  
  
 Les classes de valeur sont sealed. Si une contrainte est une classe de valeur, une autre contrainte ne peut jamais dériver de celle-ci.  
  
 Pour plus d’informations, consultez [contraintes sur les paramètres de Type générique (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3297 :  
  
```  
// C3297.cpp  
// compile with: /clr /c  
generic<class T, class U>  
where T : value class  
where U : T   // C3297  
public ref struct R {};  
```
