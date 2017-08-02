---
title: "Accès inapproprié à une union | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9e3bd236cfc6675f9476a0127977e329af3698af
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="improper-access-to-a-union"></a>Accès inapproprié à une union
**ANSI 3.3.2.3** Un accès à un membre d'un objet d'union a lieu en utilisant un membre d'un type différent  
  
 Si une union de deux types est déclarée et qu'une valeur est enregistrée, mais que l'union est accessible par l'autre type, les résultats ne sont pas fiables.  
  
 Par exemple, une union de type **float** et `int` est déclarée. Une valeur de type **float** est stockée, mais le programme y accède ultérieurement en tant que `int`. Dans ce cas, la valeur dépend du stockage interne des valeurs **float**. La valeur entière n'est pas fiable.  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, unions, énumérations et champs de bits](../c-language/structures-unions-enumerations-and-bit-fields.md)
