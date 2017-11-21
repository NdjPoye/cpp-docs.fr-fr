---
title: CBulkRowset (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CBulkRowset
- ATL.CBulkRowset
- ATL::CBulkRowset<TAccessor>
- CBulkRowset
- ATL.CBulkRowset<TAccessor>
dev_langs: C++
helpviewer_keywords: CBulkRowset class
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7208e2ecda79cf175f234499f6e69550693f182f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cbulkrowset-class"></a>CBulkRowset, classe
Récupère et manipule des lignes à fonctionner sur des données en bloc en récupérant plusieurs handles de ligne avec un seul appel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Une classe d’accesseur.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Incrémente le décompte de références.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Constructeur.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Récupère la première ligne de données, en effectuant une nouvelle extraction en bloc si nécessaire.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Déplace vers la dernière ligne.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Récupère la ligne suivante de données.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Se déplace vers la ligne précédente.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Extrait la ligne marquée par un signet ou la ligne à l’offset spécifié à partir de ce signet.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Extrait les lignes à partir d’une position décimale dans l’ensemble de lignes.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Définit la ligne actuelle (**m_nCurrentRow**) à zéro et aux versions de toutes les lignes.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Définit le nombre de handles de ligne doivent être récupérées à un seul appel.|  
  
## <a name="example"></a>Exemple  
 L’exemple suivant illustre l’utilisation de la `CBulkRowset` classe.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/cpp/cbulkrowset-class_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)