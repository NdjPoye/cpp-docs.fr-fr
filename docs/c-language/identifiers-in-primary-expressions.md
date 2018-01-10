---
title: Identificateurs dans les expressions primaires | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e507c2b7c05f9ea818f55b10d222592fe0172cc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="identifiers-in-primary-expressions"></a>Identificateurs dans les expressions primaires
Les identificateurs peuvent avoir un type intégral, **float**, `enum`, `struct`, **union**, tableau, pointeur ou fonction. Un identificateur est une expression primaire à condition d'avoir été déclaré comme désignant un objet (auquel cas il s'agit d'une l-value) ou comme fonction (auquel cas il s'agit d'un indicateur de fonction). Pour obtenir une définition de lvalue, consultez [Expressions lvalue et rvalue](../c-language/l-value-and-r-value-expressions.md).  
  
 La valeur de pointeur représentée par un identificateur de tableau n’étant pas une variable, un identificateur de tableau ne peut pas former l’opérande gauche d’une opération d’assignation et n’est donc pas une l-value modifiable.  
  
 Un identificateur déclaré comme fonction représente un pointeur dont la valeur est l'adresse de la fonction. Le pointeur adresse une fonction qui retourne une valeur d'un type spécifié. Ainsi, les identificateurs de fonction ne peuvent pas non plus être des lvalues dans les opérations d'assignation. Pour plus d’informations, consultez [Identifiers](../c-language/c-identifiers.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions primaires C](../c-language/c-primary-expressions.md)