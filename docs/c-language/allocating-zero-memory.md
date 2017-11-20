---
title: "Allocation de mémoire zéro | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9708f8939ff32f9320e7c8e803753e801ce9448f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-zero-memory"></a>Allocation de mémoire initialisée à zéro
**ANSI 4.10.3** Le comportement de la fonction `calloc`, `malloc` ou fonction `realloc` si la taille demandée est zéro  
  
 Les fonctions `calloc`, `malloc` et `realloc` acceptent zéro comme argument. Aucune mémoire réelle n'est allouée, mais un pointeur valide est retourné et le bloc de mémoire peut être modifié ultérieurement par réallocation.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)