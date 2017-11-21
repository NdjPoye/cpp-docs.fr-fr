---
title: CAccessorRowset (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CAccessorRowset
- ATL.CAccessorRowset
- ATL::CAccessorRowset
dev_langs: C++
helpviewer_keywords: CAccessorRowset class
ms.assetid: bd4f58ed-cebf-4d43-8985-1e5fcbf06953
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4b7340baabb24ef18806442504a4bd5dadf73a41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="caccessorrowset-class"></a>CAccessorRowset, classe
Encapsule un ensemble de lignes et de ses accesseurs associés dans une classe unique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CAccessorRowset :   
   public TAccessor,    
   public TRowset<TAccessor>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `TAccessor`  
 Une classe d’accesseur.  
  
 `TRowset`  
 Une classe rowset.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Lier](../../data/oledb/caccessorrowset-bind.md)|Crée des liaisons (utilisé lorsque **bBind** est défini sur false dans [CCommand::Open](../../data/oledb/ccommand-open.md)).|  
|[CAccessorRowset](../../data/oledb/caccessorrowset-caccessorrowset.md)|Constructeur.|  
|[Fermer](../../data/oledb/caccessorrowset-close.md)|Ferme l’ensemble de lignes et de tous les accesseurs.|  
|[FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md)|Libère toutes les colonnes dans l’enregistrement actif qui doivent être libérées.|  
|[GetColumnInfo](../../data/oledb/caccessorrowset-getcolumninfo.md)|Implémente [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx).|  
  
## <a name="remarks"></a>Remarques  
 Classe `TAccessor` gère l’accesseur. Classe *TRowset* gère l’ensemble de lignes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)