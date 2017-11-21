---
title: "À l’aide de plusieurs jeux de résultats d’une procédure stockée | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 787c2123981f894eb4b6ba088cfcef774b6ed6f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>Utilisation de plusieurs jeux de résultats à partir d'une seule procédure stockée
La plupart des procédures stockées retournent plusieurs jeux de résultats. Ce type de procédure stockée inclut généralement une ou plusieurs instructions select. Le consommateur doit en tenir compte pour gérer tous les jeux de résultats.  
  
### <a name="to-handle-multiple-result-sets"></a>Pour gérer les résultats multiples définit  
  
1.  Créer un `CCommand` classe avec `CMultipleResults` comme argument de modèle et avec l’accesseur de votre choix. En règle générale, il s’agit d’un accesseur dynamique ou manuel. Si vous utilisez un autre type d’accesseur, vous ne serez peut-être pas en mesure de déterminer les colonnes de sortie pour chaque ensemble de lignes.  
  
2.  Exécutez la procédure stockée comme d’habitude et liez les colonnes (consultez [comment faire pour extraire des données ?](../../data/oledb/fetching-data.md)).  
  
3.  Utiliser les données.  
  
4.  Appelez `GetNextResult` sur la `CCommand` classe. Si un autre ensemble de lignes de résultats est disponible, `GetNextResult` retourne S_OK et vous devez lier de nouveau vos colonnes si vous utilisez un accesseur manuel. Si `GetNextResult` retourne une erreur, il en existe aucun résultat supplémentaire ne jeux disponible.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des procédures stockées](../../data/oledb/using-stored-procedures.md)