---
title: Erreur du compilateur C2970 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2970
dev_langs:
- C++
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e29ed219cf0e2faba8d1c12709432a9069c5aacf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2970"></a>Erreur du compilateur C2970
'classe' : paramètre de modèle 'param' : 'arg' : une expression utilisant des objets avec une liaison interne ne peut pas être utilisée comme argument sans type  
  
 Vous ne pouvez pas utiliser le nom ou l’adresse d’une variable statique comme argument de modèle. La classe de modèle attend une valeur const qui peut être évaluée au moment de la compilation.  
  
 L’exemple suivant génère C2970 :  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```