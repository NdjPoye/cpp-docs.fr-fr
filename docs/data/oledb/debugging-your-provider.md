---
title: "Débogage de votre fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], providers
- OLE DB providers, debugging
- Visual C++ debugger, debugging providers
- Visual C++ debugger
ms.assetid: 90d4e7db-06ea-4de0-a7f4-4f3751d50d93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c5dcca9888f22aadb629bcd79a5eb73b39cddcfa
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="debugging-your-provider"></a>Débogage de votre fournisseur
Il existe deux façons de déboguer votre fournisseur :  
  
-   Étant donné que les fournisseurs sont créés dans le processus, vous pouvez créer un code de consommateur à l’aide des modèles du consommateur OLE DB et l’étape dans le fournisseur normalement.  
  
-   Vous pouvez utiliser l’utilitaire ITEST fourni avec Visual C++.  
  
### <a name="to-use-the-itest-utility"></a>Pour utiliser l’utilitaire ITEST  
  
1.  Ouvrez le projet de fournisseur.  
  
2.  Sur le **projets** menu, cliquez sur **paramètres**.  
  
3.  Dans le **Pages de propriétés** boîte de dialogue, cliquez sur le **déboguer** onglet.  
  
4.  Dans le **exécutable pour la Session de débogage** , sélectionnez l’application ITEST.  
  
5.  Définir des points d’arrêt et procédez au débogage comme d’habitude.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)