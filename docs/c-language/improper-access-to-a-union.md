---
title: "Accès inapproprié à une union | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 54eeffebcc20846666c6ebb6a2951f8d55a5b8c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="improper-access-to-a-union"></a>Accès inapproprié à une union
**ANSI 3.3.2.3** Un accès à un membre d'un objet d'union a lieu en utilisant un membre d'un type différent  
  
 Si une union de deux types est déclarée et qu'une valeur est enregistrée, mais que l'union est accessible par l'autre type, les résultats ne sont pas fiables.  
  
 Par exemple, une union de type **float** et `int` est déclarée. Une valeur de type **float** est stockée, mais le programme y accède ultérieurement en tant que `int`. Dans ce cas, la valeur dépend du stockage interne des valeurs **float**. La valeur entière n'est pas fiable.  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, unions, énumérations et champs de bits](../c-language/structures-unions-enumerations-and-bit-fields.md)