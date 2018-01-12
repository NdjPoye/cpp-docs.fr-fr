---
title: "Conversion de données non pris en charge par le fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, unsupported data types
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 438d75ad3a36c82c4f9389d4c9b65d677603f6c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="converting-data-not-supported-by-the-provider"></a>Conversion des données non prises en charge par le fournisseur
Lorsque le consommateur demande un type de données qui n’est pas pris en charge par le fournisseur, le modèle de fournisseur OLE DB de code pour `IRowsetImpl::GetData` appelle Msdadc.dll pour convertir le type de données.  
  
 Si vous implémentez une interface comme `IRowsetChange` qui nécessite une conversion de données, vous pouvez appeler Msdaenum.dll pour effectuer la conversion. Utilisez `GetData`, définie dans Atldb.h, comme un exemple.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)