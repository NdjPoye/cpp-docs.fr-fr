---
title: "Référencement d’une propriété dans votre fournisseur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1e39d012f126d44477bcb27f43b0a1119583a7ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="referencing-a-property-in-your-provider"></a>Référencement d'une propriété dans votre fournisseur
Permet de trouver le groupe de propriétés et l’ID de propriété pour la propriété que vous voulez. Pour plus d’informations, consultez [propriétés OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) dans les *de référence du programmeur OLE DB*.  
  
 L’exemple suivant suppose que vous tentez d’obtenir une propriété à partir de l’ensemble de lignes. Le code pour l’utilisation de la session ou la commande est similaire, mais utilise une autre interface.  
  
 Créer un [CDBPropSet](../../data/oledb/cdbpropset-class.md) utilisant le groupe de propriétés comme paramètre au constructeur de l’objet. Exemple :  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Appelez [AddProperty](../../data/oledb/cdbpropset-addproperty.md), en lui passant l’ID de propriété et une valeur à affecter à la propriété. Le type de la valeur dépend de la propriété que vous utilisez.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Utilisez le `IRowset` interface pour appeler **GetProperties**. Passez la propriété est définie en tant que paramètre. Voici le code final :  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  
DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  
HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)