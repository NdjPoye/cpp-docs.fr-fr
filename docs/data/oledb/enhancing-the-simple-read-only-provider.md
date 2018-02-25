---
title: "Amélioration du fournisseur en lecture seule Simple | Documents Microsoft"
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
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6eb3c583d217e421909236c09ccac6c406cf6a7c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="enhancing-the-simple-read-only-provider"></a>Amélioration du fournisseur simple accessible en lecture seule
Cette section montre comment améliorer la [fournisseur simple en lecture seule](../../data/oledb/implementing-the-simple-read-only-provider.md) créé dans la section précédente. `IRowsetLocateImpl` Crée une implémentation pour la `IRowsetLocate` de l’interface et ajoute la prise en charge des signets pour vous.  
  
 Lorsque vous avez un fournisseur opérationnel, vous souhaiterez peut-être améliorer pour rendre la mise à jour du fournisseur, gérer des transactions ou améliorer les performances de l’algorithme d’extraction de lignes. La plupart des améliorations du fournisseur impliquent l’ajout d’une interface à un objet COM existant.  
  
 L’exemple dans les rubriques suivantes améliore le mécanisme d’extraction de lignes en ajoutant le `IRowsetLocate` interface `CAgentRowset`. Les rubriques vous indiquent comment procéder pour :  
  
-   [Faites en sorte que RMyProviderRowset hérite de IRowsetLocate](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).  
  
-   [Déterminer dynamiquement les colonnes retournées au consommateur](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Création d’un fournisseur simple accessible en lecture seule](../../data/oledb/creating-a-simple-read-only-provider.md)