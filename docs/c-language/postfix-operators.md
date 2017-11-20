---
title: "Opérateurs suffixés | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ad53a3993bfc55b51cab05d5eca1a10d44bd2c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="postfix-operators"></a>Opérateurs suffixés
Les opérateurs suffixés ont la priorité la plus élevée (la liaison la plus étroite) dans l’évaluation de l’expression.  
  
## <a name="syntax"></a>Syntaxe  
 *postfix-expression* :  
 *primary-expression*  
  
 *postfix-expression*  **[**  *expression*  **]**  
  
 *postfix-expression*  **(**  *argument-expression-list* opt**)**  
  
 *postfix-expression*  **.**  *identifier*  
  
 *postfix-expression*  **->**  *identifier*  
  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 Dans ce niveau de priorité, les opérateurs sont les indices de tableau, les appels de fonction, les membres de structure et d'union, et les opérateurs d'incrémentation et de décrémentation suffixés.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs C](../c-language/c-operators.md)