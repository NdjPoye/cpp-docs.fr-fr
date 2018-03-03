---
title: Taille de tableau la plus grande | Microsoft Docs
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
ms.assetid: 4c782cf6-73f3-40b0-b306-229d22da4ee1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d318c03f8fb652331830b913dbd0b2824afa37a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="largest-array-size"></a>Taille de tableau la plus grande
**ANSI 3.3.3.4, 4.1.1** Le type d’entier requis pour conserver la taille maximale d’un tableau, c’est-à-dire la taille de **size_t**.  
  
 Le typedef `size_t` est un `unsigned int` sur la plateforme x86 32 bits. Sur les plateformes 64 bits, le typedef `size_t` est un **unsigned __int64**.  
  
## <a name="see-also"></a>Voir aussi  
 [Tableaux et pointeurs](../c-language/arrays-and-pointers.md)