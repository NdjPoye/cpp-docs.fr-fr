---
title: "Interfaces de l’objet de l’ensemble de lignes | Documents Microsoft"
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
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211fb5bbd0a950eff5f954d1c23b3dc993badb0d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="rowset-object-interfaces"></a>Interfaces de l'objet rowset
Le tableau suivant montre les interfaces obligatoires et facultatives définies par OLE DB pour un objet d’ensemble de lignes.  
  
|Interface|Obligatoire ?|Implémentée par les modèles OLE DB ?|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)|Obligatoire|Oui|  
|[IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Obligatoire|Oui|  
|[IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx)|Obligatoire|Oui|  
|[IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)|Obligatoire|Oui|  
|[IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx)|Obligatoire|Oui|  
|[IChapteredRowset](https://msdn.microsoft.com/en-us/library/ms718180.aspx)|Facultatif|Non|  
|[IColumnsInfo2](https://msdn.microsoft.com/en-us/library/ms712953.aspx)|Facultatif|Non|  
|[IColumnsRowset](https://msdn.microsoft.com/en-us/library/ms722657.aspx)|Facultatif|Non|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Facultatif|Oui (via ATL)|  
|[IDBAsynchStatus](https://msdn.microsoft.com/en-us/library/ms709832.aspx)|Facultatif|Non|  
|[IGetRow](https://msdn.microsoft.com/en-us/library/ms718047.aspx)|Facultatif|Non|  
|[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)|Facultatif|Oui|  
|[IRowsetChapterMember](https://msdn.microsoft.com/en-us/library/ms725430.aspx)|Facultatif|Non|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/en-us/library/ms709700.aspx)|Facultatif|Non|  
|[IRowsetFind](https://msdn.microsoft.com/en-us/library/ms724221.aspx)|Facultatif|Non|  
|[IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx)|Facultative (mais requise pour les fournisseurs de niveau 0)|Oui|  
|[IRowsetIndex](https://msdn.microsoft.com/en-us/library/ms719604.aspx)|Facultatif|Non|  
|[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)|Facultatif|Oui|  
|[IRowsetRefresh](https://msdn.microsoft.com/en-us/library/ms714892.aspx)|Facultatif|Non|  
|[IRowsetScroll](https://msdn.microsoft.com/en-us/library/ms712984.aspx)|Facultatif|Non|  
|[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)|Facultatif|Oui|  
|[IRowsetView](https://msdn.microsoft.com/en-us/library/ms709755.aspx)|Facultatif|Non|  
|[ISupportErrorInfo](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Facultatif|Oui|  
|[IRowsetBookmark](https://msdn.microsoft.com/en-us/library/ms714246.aspx)|Facultatif|Non|  
  
 L’objet d’ensemble de lignes générées par l’Assistant implémente `IAccessor`, `IRowset`, et `IRowsetInfo` via l’héritage. Le `IAccessorImpl` lie les deux colonnes de sortie. Le `IRowset` interface gère les extractions de lignes et de données. Le `IRowsetInfo` interface gère les propriétés de l’ensemble de lignes.  
  
## <a name="see-also"></a>Voir aussi  
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)