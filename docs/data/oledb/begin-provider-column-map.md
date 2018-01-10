---
title: BEGIN_PROVIDER_COLUMN_MAP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROVIDER_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_PROVIDER_COLUMN_MAP macro
ms.assetid: 506b8c0f-6be9-4c97-ba81-c4b7f7d428fa
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 05b70429c127927c7b436980f573efedee14707e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="beginprovidercolumnmap"></a>BEGIN_PROVIDER_COLUMN_MAP
Marque le début des entrées de mappage de colonne fournisseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BEGIN_PROVIDER_COLUMN_MAP(  
theClass   
)  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `theClass`  
 [in] Le nom de la classe à que laquelle appartient cette carte.  
  
## <a name="example"></a>Exemple  
 Voici un exemple de mappage de colonne fournisseur :  
  
 [!code-cpp[NVC_OLEDB_Provider#4](../../data/oledb/codesnippet/cpp/begin-provider-column-map_1.h)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)