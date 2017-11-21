---
title: "Définition d’une règle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e720613dd4d918b2b697a6ff21a8950f0c5adc2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="defining-a-rule"></a>Définition d'une règle
Le *fromext* représente l’extension d’un fichier dépendant, et *toext* représente l’extension d’un fichier cible.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>Remarques  
 Les extensions ne respectent pas la casse. Les macros peuvent être appelées pour représenter *fromext* et *toext*; les macros sont développées pendant le prétraitement. Le point (.) précédent *fromext* doit apparaître au début de la ligne. Le signe deux-points ( :) est précédé de zéro ou plusieurs espaces ou des tabulations. Il peut être suivi que par des espaces ou onglets, un point-virgule ( ;) pour spécifier une commande, un signe dièse (#) pour spécifier un commentaire ou un caractère de saut de ligne. Aucuns autres espaces ne sont autorisés. Les commandes sont spécifiées comme dans les blocs de description.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Chemins de recherche dans les règles](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Règles d’inférence](../build/inference-rules.md)