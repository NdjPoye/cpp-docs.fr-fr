---
title: "C2062 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2062
dev_langs: C++
helpviewer_keywords: C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e4a006bed55f16e6ed94c3b5ed9415320acb86fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2062"></a>C2062 d’erreur du compilateur
type inattendu ' type'  
  
 Le compilateur ne vous attendiez pas un nom de type.  
  
 L’exemple suivant génère l’erreur C2062 :  
  
```  
// C2062.cpp  
// compile with: /c  
struct A {  : int l; };   // C2062  
struct B { private: int l; };   // OK  
```  
  
 L’erreur C2062 peut également se produire en raison de la façon dont le compilateur gère les types indéfinis dans la liste de paramètres d’un constructeur. Si le compilateur rencontre un type indéfini de (mal orthographié ?), il suppose que le constructeur est une expression et émet l’erreur C2062. Pour résoudre, utilisez uniquement des types définis dans une liste de paramètres du constructeur.