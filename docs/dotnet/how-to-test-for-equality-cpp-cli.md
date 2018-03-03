---
title: "Comment : tester l’égalité (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- equality, testing for
ms.assetid: 9115e298-9f75-452d-bdfb-6eeb0fa0b3c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 19b573ca0069031cda6d7c8108d51f8bf4fa83ce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-test-for-equality-ccli"></a>Comment : tester l'égalité (C++/CLI)
Dans l’exemple suivant, un test d’égalité qui utilise les Extensions managées pour C++ est basé sur ce que les handles font référence.  
  
## <a name="example"></a>Exemple  
  
```  
// mcppv2_equality_test.cpp  
// compile with: /clr /LD  
using namespace System;  
  
bool Test1() {  
   String ^ str1 = "test";  
   String ^ str2 = "test";  
   return (str1 == str2);  
}  
```  
  
 Le langage intermédiaire de ce programme montre que la valeur de retour est implémentée à l’aide d’un appel à op_Equality.  
  
```  
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,  
                                                               string)  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Types managés (C++-CLI)](../dotnet/managed-types-cpp-cli.md)