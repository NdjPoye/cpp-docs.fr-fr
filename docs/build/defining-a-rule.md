---
title: "Définition d’une règle | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, inference rules
- defining inference rules
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0d6ca616e3685db36d6d24b339a860eab4c6150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="defining-a-rule"></a>Définition d'une règle
Le *fromext* représente l’extension d’un fichier dépendant, et *toext* représente l’extension d’un fichier cible.  
  
```  
.fromext.toext:  
   commands  
```  
  
## <a name="remarks"></a>Notes  
 Les extensions ne respectent pas la casse. Les macros peuvent être appelées pour représenter *fromext* et *toext*; les macros sont développées pendant le prétraitement. Le point (.) précédent *fromext* doit apparaître au début de la ligne. Le signe deux-points ( :) est précédé de zéro ou plusieurs espaces ou des tabulations. Il peut être suivi que par des espaces ou onglets, un point-virgule ( ;) pour spécifier une commande, un signe dièse (#) pour spécifier un commentaire ou un caractère de saut de ligne. Aucuns autres espaces ne sont autorisés. Les commandes sont spécifiées comme dans les blocs de description.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Chemins de recherche dans les règles](../build/search-paths-in-rules.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Règles d’inférence](../build/inference-rules.md)