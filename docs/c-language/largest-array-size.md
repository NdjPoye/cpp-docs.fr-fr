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
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aca2748ca834a16b1297b78ccc10d8e031cda029
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="largest-array-size"></a>Taille de tableau la plus grande
**ANSI 3.3.3.4, 4.1.1** Le type d’entier requis pour conserver la taille maximale d’un tableau, c’est-à-dire la taille de **size_t**.  
  
 Le typedef `size_t` est un `unsigned int` sur la plateforme x86 32 bits. Sur les plateformes 64 bits, le typedef `size_t` est un **unsigned __int64**.  
  
## <a name="see-also"></a>Voir aussi  
 [Tableaux et pointeurs](../c-language/arrays-and-pointers.md)
