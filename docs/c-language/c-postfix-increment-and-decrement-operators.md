---
title: "Opérateurs suffixés d’incrémentation et de décrémentation C | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6279ede332ffbcc12db4f8c72e17fe9050cc96e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="c-postfix-increment-and-decrement-operators"></a>Opérateurs suffixés d'incrémentation et de décrémentation C
Les opérandes des opérateurs d’incrémentation et de décrémentation sont des types scalaires qui sont des valeurs lvalue modifiables.  
  
## <a name="syntax"></a>Syntaxe  
 *postfix-expression* :  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 Le résultat de l’opération d’incrémentation ou de décrémentation suffixée est la valeur de l’opérande. Une fois le résultat obtenu, la valeur de l'opérande est incrémentée (ou décrémentée). Le code suivant illustre l'opérateur d'incrémentation suffixée.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 Dans cet exemple, la variable `var` est comparée à 0, puis incrémentée. Si `var` avait une valeur positive avant d'être incrémentée, l'instruction suivante est exécutée. D'abord, la valeur de l'objet pointé par `q`est assignée à l'objet pointé par `p`. Ensuite, `q` et `p` sont incrémentés.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs suffixés d’incrémentation et de décrémentation : ++ et --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)