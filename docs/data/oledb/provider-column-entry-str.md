---
title: PROVIDER_COLUMN_ENTRY_STR | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_STR
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_STR macro
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8f26311d3f84c28983a9d53985dbdde16f2c47cf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="providercolumnentrystr"></a>PROVIDER_COLUMN_ENTRY_STR
Représente une colonne spécifique pris en charge par le fournisseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
PROVIDER_COLUMN_ENTRY_STR(  
name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>Paramètres  
 *name*  
 [in] Le nom de colonne.  
  
 `ordinal`  
 [in] Le numéro de colonne. Sauf si la colonne est une colonne de signet, le numéro de colonne ne doit pas être 0.  
  
 `member`  
 [in] La variable membre de la classe de données qui stocke les données.  
  
## <a name="remarks"></a>Remarques  
 Utilisez cette macro, lorsque les données de colonne sont supposées être [DBTYPE_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## <a name="example"></a>Exemple  
 Consultez [BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)