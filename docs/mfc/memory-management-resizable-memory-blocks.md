---
title: "Gestion de la m&#233;moire&#160;: blocs de m&#233;moire redimensionnables | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "blocs, allocation de mémoire"
  - "allocation de mémoire, taille de bloc de mémoire"
  - "blocs de mémoire, allouer"
  - "blocs de mémoire, redimensionnables"
  - "mémoire, altération"
  - "blocs de mémoire redimensionnables"
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Gestion de la m&#233;moire&#160;: blocs de m&#233;moire redimensionnables
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs de **new** et de **supprimer**, décrites dans l'article [Gestion de la mémoire : Exemples](../mfc/memory-management-examples.md), sont parfaits pour allouer et libérer les blocs de mémoire de taille fixe et des objets.  Occasionnellement, votre application peut nécessiter des blocs de mémoire redimensionnables.  Vous devez utiliser les fonctionnalités standard de la bibliothèque Runtime C [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), et [disponible](../c-runtime-library/reference/free.md) pour gérer les blocs de mémoire redimensionnables sur le segment.  
  
> [!IMPORTANT]
>  Combiner les opérateurs de **new** et de **supprimer** avec les fonctions d'allocation de mémoire redimensionnables dans le même bloc de mémoire entraîne la mémoire endommagée dans la version de débogage de MFC.  Vous ne devez pas utiliser `realloc` sur un bloc de mémoire allouée à **new**.  De même, vous ne devez pas allouer un bloc de mémoire à l'aide de l'opérateur de **new** et le supprimer avec **free**, ou utilisez l'opérateur de **supprimer** sur un bloc de mémoire allouée à `malloc`.  
  
## Voir aussi  
 [Gestion de la mémoire : allocation de tas](../mfc/memory-management-heap-allocation.md)