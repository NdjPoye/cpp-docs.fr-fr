---
title: CBulkRowset::MoveToBookmark | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBulkRowset<TAccessor>::MoveToBookmark
- CBulkRowset.MoveToBookmark
- MoveToBookmark
- ATL.CBulkRowset.MoveToBookmark
- CBulkRowset::MoveToBookmark
- ATL::CBulkRowset<TAccessor>::MoveToBookmark
- ATL::CBulkRowset::MoveToBookmark
dev_langs: C++
helpviewer_keywords: MoveToBookmark method
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 883bea68992d646fd7ee82257f794394a1d2ffc4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cbulkrowsetmovetobookmark"></a>CBulkRowset::MoveToBookmark
Extrait la ligne marquée par un signet ou la ligne à l’offset spécifié (`lSkip`) à partir de ce signet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `bookmark`  
 [in] Un signet est l’emplacement à partir duquel vous souhaitez extraire des données.  
  
 `lSkip`  
 [in] Le nombre de lignes à partir du signet à la ligne de la cible. Si `lSkip` est égal à zéro, la première ligne extraite est la ligne marquée par un signet. Si `lSkip` est 1, la première ligne extraite est la ligne après la ligne marquée par un signet. Si `lSkip` est -1, la première ligne extraite est la ligne avant la ligne marquée par un signet.  
  
## <a name="return-value"></a>Valeur de retour  
 Consultez [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)