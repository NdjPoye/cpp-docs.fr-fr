---
title: CDynamicAccessor::SetBlobHandling | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs: C++
helpviewer_keywords: SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 02b9be4b187f55d9bfb8f3ee5e572f682742f538
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
Définit l’objet BLOB de valeur de la ligne en cours de traitement.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `eBlobHandling`  
 Spécifie la façon dont les données BLOB doit être gérée. Elle peut prendre les valeurs suivantes :  
  
-   **DBBLOBHANDLING_DEFAULT**: gérer les données de colonne supérieures à `nBlobSize` (comme défini par `SetBlobSizeLimit`) en tant que données d’objets BLOB et récupérer par le biais d’un `ISequentialStream` ou `IStream` objet. Cette option va tenter de lier chaque colonne contenant des données plus importante que `nBlobSize` ou répertoriés sous la forme **DBTYPE_IUNKNOWN** en tant que données d’objet BLOB.  
  
-   **DBBLOBHANDLING_NOSTREAMS**: gérer les données de colonne supérieures à `nBlobSize` (comme défini par `SetBlobSizeLimit`) en tant que données d’objets BLOB et les récupérer via la référence dans la mémoire allouée par le fournisseur, appartenant à un consommateur. Cette option est utile pour les tables qui ont plus d’une colonne BLOB, et le fournisseur prend en charge qu’un seul `ISequentialStream` objet par l’accesseur.  
  
-   **DBBLOBHANDLING_SKIP**: ignorer (ne pas lier) les colonnes éligibles comme contenant des objets BLOB (l’accesseur ne sera pas lier ou récupérer la valeur de colonne, mais il sera toujours récupérer l’état de colonne et la longueur).  
  
## <a name="remarks"></a>Notes  
 Vous devez appeler `SetBlobHandling` avant d’appeler **ouvrir**.  
  
 La méthode de constructeur [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) définit l’objet BLOB de valeur de la gestion des **DBBLOBHANDLING_DEFAULT**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)