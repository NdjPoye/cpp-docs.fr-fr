---
title: "Littéraux chaîne dans les expressions primaires | Microsoft Docs"
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
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0920280f672b1c45d317ade4c592a6b93356fb8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="string-literals-in-primary-expressions"></a>Littéraux chaîne dans les expressions primaires
Un littéral de chaîne est un caractère, un caractère élargi ou une séquence de caractères adjacents placés entre guillemets. Étant donné que les littéraux de chaîne et tous leurs éléments ne sont pas des variables, ils peuvent constituer l'opérande gauche d'une opération d'assignation. Le type d'un littéral de chaîne est un tableau de `char` (ou un tableau de `wchar_t` pour les littéraux de chaîne étendus). Les tableaux présents dans les expressions sont convertis en pointeurs. Pour plus d'informations sur les chaînes, consultez [Littéraux de chaîne](../c-language/c-string-literals.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions primaires C](../c-language/c-primary-expressions.md)