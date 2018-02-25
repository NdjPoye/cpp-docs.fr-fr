---
title: CDataSource::OpenWithServiceComponents | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- OpenWithServiceComponents method
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0967888557d1a62952e0d1f0c23ee83b7d03550b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdatasourceopenwithservicecomponents"></a>CDataSource::OpenWithServiceComponents
Ouvre un objet source de données à l'aide des composants de service d'oledb32.dll.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  


HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `clsid`  
 [in] Le **CLSID** d’un fournisseur de données.  
  
 `szProgID`  
 [in] ID de programme d'un fournisseur de données.  
  
 `pPropset`  
 [in] Un pointeur vers un tableau de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) les structures contenant des propriétés et valeurs à définir. Consultez [jeux de propriétés et des groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans les *de référence du programmeur OLE DB* dans le Kit de développement logiciel Windows. Si l'objet source de données est initialisé, les propriétés doivent appartenir au groupe de propriétés Source de données. Si la même propriété est spécifiée plusieurs fois dans `pPropset`, la valeur utilisée varie en fonction du fournisseur. Si `ulPropSets` est égal à zéro, ce paramètre est ignoré.  
  
 `ulPropSets`  
 [in] Le nombre de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures passées dans le *pPropSet* argument. Si la valeur est égale à zéro, le fournisseur ignore `pPropset`.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 Cette méthode ouvre un objet source de données à l’aide des composants de service d’oledb32.dll ; cette DLL contient l’implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l’inscription de transaction automatique, etc. Pour plus d’informations, consultez « Services OLE DB » dans la référence du programmeur OLE DB à l’adresse [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)