---
title: BEGIN_PROPERTY_SET_EX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_PROPERTY_SET_EX
dev_langs: C++
helpviewer_keywords: BEGIN_PROPERTY_SET_EX macro
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ede0dac08233d82decb23064e47b61cbd9a05da1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="beginpropertysetex"></a>BEGIN_PROPERTY_SET_EX
Marque le début d’une propriété défini dans une propriété de mappage d’ensemble.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### <a name="parameters"></a>Paramètres  
 `guid`  
 [in] La propriété GUID.  
  
 `flags`  
 [in] **UPROPSET_HIDDEN** pour tous les jeux de propriétés que vous ne souhaitez pas exposer, ou **UPROPSET_PASSTHROUGH** pour un fournisseur d’exposer les propriétés définies à l’extérieur de la portée du fournisseur.  
  
## <a name="example"></a>Exemple  
 Voir [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)