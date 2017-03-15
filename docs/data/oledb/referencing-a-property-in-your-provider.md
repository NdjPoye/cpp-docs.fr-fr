---
title: "R&#233;f&#233;rencement d&#39;une propri&#233;t&#233; dans votre fournisseur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fournisseurs OLE DB, propriétés"
  - "références, propriétés dans les fournisseurs"
  - "référencer les propriétés dans les fournisseurs"
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#233;f&#233;rencement d&#39;une propri&#233;t&#233; dans votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Recherchez le groupe de propriétés et l'ID de propriété de la propriété qui vous intéresse.  Pour plus d'informations, consultez [Propriétés OLE DB](https://msdn.microsoft.com/en-us/library/ms722734.aspx) dans *OLE DB Programmer's Reference*.  
  
 L'exemple suivant suppose que vous essayez d'obtenir une propriété à partir du jeu de lignes.  Le code d'utilisation de la session ou de la commande est similaire, sauf qu'il utilise une interface différente.  
  
 Créez un objet [CDBPropSet](../../data/oledb/cdbpropset-class.md) à l'aide du groupe de propriétés en tant que paramètre du constructeur.  Par exemple :  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Appelez [AddProperty](../../data/oledb/cdbpropset-addproperty.md), en lui passant l'ID de propriété et une valeur à assigner à la propriété.  Le type de valeur dépend de la propriété que vous utilisez.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Utilisez l'interface `IRowset` pour appeler **GetProperties**.  Passez le jeu de propriétés en tant que paramètre.  Voici le code final :  
  
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
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)