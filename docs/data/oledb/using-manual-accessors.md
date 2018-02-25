---
title: Utilisation des accesseurs manuels | Documents Microsoft
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
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e7d6bd8f0228103e4899e6bc24f6d67af0f3fdb4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="using-manual-accessors"></a>Utilisation des accesseurs manuels
Il existe quatre opérations lors du traitement d’une commande inconnue :  
  
-   Déterminer les paramètres  
  
-   Exécutez la commande  
  
-   Déterminer les colonnes de sortie  
  
-   S’il existe plusieurs ensembles de lignes de retour  
  
 Pour ce faire, avec les modèles du consommateur OLE DB, utilisez la `CManualAccessor` classe et procédez comme suit :  
  
1.  Ouvrir un `CCommand` avec l’objet `CManualAccessor` comme paramètre de modèle.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Interrogez la session pour le **IDBSchemaRowset** interface et utiliser l’ensemble de lignes de paramètres de procédure. Si le **IDBSchemaRowset** interface n’est pas disponible, recherchez le `ICommandWithParameters` interface. Appelez `GetParameterInfo` pour plus d’informations. Si aucune interface n’est disponible, vous pouvez supposer qu’aucun paramètre.  
  
3.  Pour chaque paramètre, appelez `AddParameterEntry` pour ajouter les paramètres et les définir.  
  
4.  Ouvrir l’ensemble de lignes, mais la valeur du paramètre de liaison **false**.  
  
5.  Appelez `GetColumnInfo` pour récupérer les colonnes de sortie. Utilisez `AddBindEntry` pour ajouter la colonne de sortie à la liaison.  
  
6.  Appelez `GetNextResult` pour déterminer si plusieurs ensembles de lignes sont disponibles. Répétez les étapes 2 à 5.  
  
 Pour obtenir un exemple d’accesseur manuel, consultez **CDBListView::CallProcedure** dans les [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) exemple.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)