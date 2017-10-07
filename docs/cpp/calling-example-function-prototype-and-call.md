---
title: "Exemple d’appel : Prototype et appel de fonction | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 897771dbe2d769744bd5dc119083c9db243d56c0
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="calling-example-function-prototype-and-call"></a>Exemple d'appel : Prototype et appel de fonction
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 L'exemple suivant montre les résultats d'un appel de fonction effectué à l'aide de différentes conventions d'appel.  
  
 Cet exemple repose sur la structure de fonction suivante. Remplacez `calltype` par la convention d'appel appropriée.  
  
```  
void    calltype MyFunc( char c, short s, int i, double f );  
.  
.  
.  
void    MyFunc( char c, short s, int i, double f )  
    {  
    .  
    .  
    .  
    }  
.  
.  
.  
MyFunc ('x', 12, 8192, 2.7183);  
```  
  
 Pour plus d’informations, consultez [résultats de l’appel exemple](../cpp/results-of-calling-example.md).  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions d’appel](../cpp/calling-conventions.md)
