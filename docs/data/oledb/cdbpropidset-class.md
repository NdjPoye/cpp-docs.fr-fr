---
title: Cdbpropidset, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs: C++
helpviewer_keywords: CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c75b357b912adc67351510e745fa46f246a74b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet, classe
Hérite de la **DBPROPIDSET** structurer et ajoute un constructeur qui initialise les champs clés, ainsi que les [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) accéder à la méthode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Ajoute une propriété à la propriété ID définie.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|Constructeur.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|Définit le GUID de l’ID de propriété de jeu.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur =](../../data/oledb/cdbpropidset-operator-equal.md)|Assigne le contenu d’une propriété ID définie à un autre.|  
  
## <a name="remarks"></a>Notes  
 Utilisation de consommateurs OLE DB **DBPROPIDSET** structures pour passer un tableau d’ID de propriété pour laquelle le consommateur souhaite obtenir des informations sur les propriétés. Les propriétés identifiées dans un seul [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) structure appartiennent au jeu d’une propriété.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)