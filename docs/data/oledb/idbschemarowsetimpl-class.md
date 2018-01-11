---
title: IDBSchemaRowsetImpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDBSchemaRowsetImpl
dev_langs: C++
helpviewer_keywords: IDBSchemaRowsetImpl class
ms.assetid: bd7bf0d7-a1c6-4afa-88e3-cfdbdf560703
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b4f451fa408f2f6470281206e5de3670d069b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="idbschemarowsetimpl-class"></a>IDBSchemaRowsetImpl (classe)
Fournit l’implémentation pour les ensembles de lignes de schéma.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class SessionClass>  
class ATL_NO_VTABLE IDBSchemaRowsetImpl : public IDBSchemaRowset  
```  
  
#### <a name="parameters"></a>Paramètres  
 `SessionClass`  
 Classe par laquelle `IDBSchemaRowsetImpl` est hérité. En général, cette classe est la classe session de l’utilisateur.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md)|Vérifie la validité des restrictions par rapport à un ensemble de lignes de schéma.|  
|[CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md)|Implémente une fonction du créateur d’objet COM pour l’objet spécifié par le paramètre de modèle.|  
|[SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)|Spécifie les restrictions que vous prenez en charge sur un ensemble de lignes de schéma particulier.|  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md)|Retourne un ensemble de lignes de schéma.|  
|[GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md)|Retourne une liste d’ensembles de lignes de schéma accessibles par [IDBSchemaRowsetImpl::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md).|  
  
## <a name="remarks"></a>Notes  
 Cette classe implémente l’interface [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) et la fonction de créateur mise en modèle [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md).  
  
 OLE DB utilise les ensembles de lignes de schéma pour retourner des données à propos des données d’un fournisseur. Ces données sont souvent appelées « métadonnées ». Par défaut, un fournisseur doit toujours prendre en charge `DBSCHEMA_TABLES`, **DBSCHEMA_COLUMNS**et **DBSCHEMA_PROVIDER_TYPES**, comme décrit dans [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) dans les *Informations de référence du programmeur OLE DB*. Les ensembles de lignes de schéma sont désignés dans un mappage de schéma. Pour plus d’informations sur les entrées de mappage de schéma, consultez [SCHEMA_ENTRY](../../data/oledb/schema-entry.md).  
  
 L’Assistant Fournisseur OLE DB, dans l’Assistant Objet ATL, génère automatiquement le code pour les ensembles de lignes de schéma dans votre projet. (Par défaut, l’Assistant prend en charge les ensembles de lignes de schéma obligatoires précédemment mentionnés.) Quand vous créez un consommateur à l’aide de l’Assistant Objet ATL, l’Assistant utilise les ensembles de lignes de schéma pour lier les données appropriées à un fournisseur. Si vous n’implémentez pas vos ensembles de lignes de schéma pour fournir les métadonnées correctes, l’Assistant ne lie pas les bonnes données.  
  
 Pour plus d’informations sur la prise en charge des ensembles de lignes de schéma dans votre fournisseur, consultez [Prise en charge des ensembles de lignes de schéma](../../data/oledb/supporting-schema-rowsets.md).  
  
 Pour plus d’informations sur les ensembles de lignes de schéma, consultez [Ensembles de lignes de schéma](https://msdn.microsoft.com/en-us/library/ms712921.aspx) dans les *Informations de référence du programmeur OLE DB*.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Membres IDBSchemaRowsetImpl (classe)](http://msdn.microsoft.com/en-us/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [Classes d’ensemble de lignes de schéma et Classes Typedef](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)   
 [Prise en charge des ensembles de lignes de schéma](../../data/oledb/supporting-schema-rowsets.md)