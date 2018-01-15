---
title: "Gestion de la mémoire : Blocs de mémoire redimensionnables | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fce06d27a091ad1740c882367358cf69a6dc3e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-resizable-memory-blocks"></a>Gestion de la mémoire : blocs de mémoire redimensionnables
Le **nouveau** et **supprimer** opérateurs, décrites dans l’article [gestion de la mémoire : exemples](../mfc/memory-management-examples.md), sont correctes pour allouer et libérer des blocs de mémoire de taille fixe et objets. Parfois, votre application peut avoir besoin de blocs de mémoire redimensionnables. Vous devez utiliser les fonctions de bibliothèque Runtime C standard [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), et [libre](../c-runtime-library/reference/free.md) pour gérer les blocs de mémoire redimensionnables sur le tas.  
  
> [!IMPORTANT]
>  Mélange les **nouveau** et **supprimer** opérateurs avec les fonctions d’allocation de mémoire redimensionnables sur le même bloc de mémoire entraîne une mémoire endommagée dans la version Debug des MFC. Vous ne devez pas utiliser `realloc` sur un bloc de mémoire alloué avec **nouveau**. De même, vous ne devez pas allouer un bloc de mémoire avec la **nouveau** opérateur et le supprimer avec **libre**, ou utilisez le **supprimer** opérateur sur un bloc de mémoire allouée avec `malloc`.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de la mémoire : allocation de tas](../mfc/memory-management-heap-allocation.md)

