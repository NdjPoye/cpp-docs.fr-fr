---
title: CRowset::MoveToBookmark | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::MoveToBookmark
- ATL::CRowset<TAccessor>::MoveToBookmark
- ATL.CRowset.MoveToBookmark
- ATL.CRowset<TAccessor>.MoveToBookmark
- MoveToBookmark
- CRowset::MoveToBookmark
- CRowset.MoveToBookmark
- CRowset<TAccessor>::MoveToBookmark
dev_langs: C++
helpviewer_keywords: MoveToBookmark method
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 08e570d6d2cbc8c5943ce0591c280b74be573e2a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovetobookmark"></a>CRowset::MoveToBookmark
Extrait la ligne marquée par un signet ou la ligne à l’offset spécifié (`lSkip`) à partir de ce signet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT MoveToBookmark(   
   const CBookmarkBase& bookmark,   
   LONG lSkip = 0    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `bookmark`  
 [in] Un signet est l’emplacement à partir duquel vous souhaitez extraire des données.  
  
 `lSkip`  
 [in] Le nombre de lignes à partir du signet à la ligne de la cible. Si `lSkip` est égal à zéro, la première ligne extraite est la ligne marquée par un signet. Si `lSkip` est 1, la première ligne extraite est la ligne après la ligne marquée par un signet. Si `lSkip` est -1, la première ligne extraite est la ligne avant la ligne marquée par un signet.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode requiert l’interface facultative `IRowsetLocate`, qui ne peut pas être pris en charge sur tous les fournisseurs ; si c’est le cas, la méthode retourne **E_NOINTERFACE**. Vous devez également définir **DBPROP_IRowsetLocate** à `VARIANT_TRUE` et **DBPROP_CANFETCHBACKWARDS** à `VARIANT_TRUE` avant d’appeler **ouvrir** sur la table ou de la commande qui contient l’ensemble de lignes.  
  
 Pour plus d’informations sur l’utilisation de signets dans des consommateurs, consultez [à l’aide de signets](../../data/oledb/using-bookmarks.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CRowset (classe)](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)