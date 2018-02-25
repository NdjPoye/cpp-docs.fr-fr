---
title: PROPERTY_INFO_ENTRY_EX | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROPERTY_INFO_ENTRY_EX
dev_langs:
- C++
helpviewer_keywords:
- PROPERTY_INFO_ENTRY_EX macro
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6696067e94a10e57d52f5875b712f100c5ac6902
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="propertyinfoentryex"></a>PROPERTY_INFO_ENTRY_EX
Représente une propriété spécifique dans un jeu de propriétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
PROPERTY_INFO_ENTRY_EX(dwPropID  
, vt, dwFlags, value, options )  
```  
  
#### <a name="parameters"></a>Paramètres  
 *dwPropID*  
 [in] Valeur [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) qui peut être utilisée en combinaison avec le GUID du jeu de propriétés pour identifier une propriété.  
  
 *vt*  
 [in] [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) de cette entrée de propriété.  
  
 `dwFlags`  
 [in] Valeur [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) décrivant cette entrée de propriété.  
  
 *valeur*  
 [in] Valeur de propriété de type `DWORD`.  
  
 `options`  
 **DBPROPOPTIONS_REQUIRED** ou **DBPROPOPTIONS_SETIFCHEAP**. Normalement, un fournisseur n’a pas besoin de définir `options` , car celui-ci est défini par le consommateur.  
  
## <a name="remarks"></a>Notes  
 Avec cette macro, vous pouvez spécifier directement la valeur de propriété de type `DWORD` , ainsi que les options et les indicateurs. Pour affecter simplement à une propriété une valeur par défaut définie dans ATLDB.H, utilisez [PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md). Pour affecter à une propriété une valeur de votre choix, sans définir aucune option ou indicateur, utilisez [PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## <a name="example"></a>Exemple  
 Voir [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d’un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)