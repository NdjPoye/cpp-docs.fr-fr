---
title: "Type pour les littéraux de chaîne | Microsoft Docs"
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
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
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
ms.openlocfilehash: 8e8d285bf85c711bd6adcbdb45c6384ea2309dc0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="type-for-string-literals"></a>Type pour les littéraux de chaîne
Les littéraux de chaîne ont un tableau de type `char` (autrement dit, **char[ ]**). (Les chaînes à caractères larges ont un tableau de type `wchar_t` (autrement dit, **wchar_t[ ]**).) Cela signifie qu'une chaîne est un tableau avec des éléments de type `char`. Le nombre d'éléments du tableau est égal au nombre de caractères dans la chaîne plus un pour le caractère null de fin.  
  
## <a name="see-also"></a>Voir aussi  
 [Littéraux de chaîne C](../c-language/c-string-literals.md)
