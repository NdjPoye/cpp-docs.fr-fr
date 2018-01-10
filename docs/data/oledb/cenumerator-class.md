---
title: CEnumerator, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CEnumerator
dev_langs: C++
helpviewer_keywords: CEnumerator class
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a64ac02e7b16bfab70966ffaf2a1897ae955f8c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cenumerator-class"></a>CEnumerator, classe
Utilise un objet énumérateur OLE DB, qui expose le [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) interface pour retourner un ensemble de lignes décrivant toutes les sources de données et les énumérateurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Rechercher](../../data/oledb/cenumerator-find.md)|Recherche via des fournisseurs disponibles (sources de données) en recherchant une avec le nom spécifié.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Récupère le `IMoniker` interface pour l’enregistrement actif.|  
|[Ouvrir](../../data/oledb/cenumerator-open.md)|Ouvre l’énumérateur.|  
  
## <a name="remarks"></a>Notes  
 Vous pouvez récupérer le **ISourcesRowset** données indirectement à partir de cette classe.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :**atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [DBViewer](../../visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)