---
title: "Dépassement négatif de valeurs à virgule flottante | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f74624f935c9a1384c1c4992004b12c7847e9fd2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="underflow-of-floating-point-values"></a>Dépassement des valeurs à virgule flottante
**ANSI 4.5.1** Indique si les fonctions mathématiques définissent l'expression d'entier `errno` sur la valeur de la macro `ERANGE` sur les erreurs de plage de dépassement de capacité négatif  
  
 Un dépassement de capacité négatif à virgule flottante ne définit pas l'expression `errno` sur `ERANGE`. Lorsqu'une valeur s'approche de zéro et effectue finalement un dépassement de capacité négatif, la valeur est définie sur zéro.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)