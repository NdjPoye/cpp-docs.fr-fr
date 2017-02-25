---
title: "CDataSource::OpenWithServiceComponents | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::OpenWithServiceComponents"
  - "OpenWithServiceComponents"
  - "CDataSource.OpenWithServiceComponents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithServiceComponents (méthode)"
ms.assetid: 49c1d037-36ae-4fde-8e54-ced623abe1a9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDataSource::OpenWithServiceComponents
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre un objet source de données à l'aide des composants de service d'oledb32.dll.  
  
## Syntaxe  
  
```  
  
        HRESULT OpenWithServiceComponents (  
   const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
HRESULT OpenWithServiceComponents (  
   LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1   
);  
```  
  
#### Paramètres  
 `clsid`  
 \[in\] **CLSID** d'un fournisseur de données.  
  
 `szProgID`  
 \[in\] ID de programme d'un fournisseur de données.  
  
 `pPropset`  
 \[in\] Pointeur désignant un tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) contenant les propriétés et les valeurs à définir.  Consultez [Jeux de propriétés et groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans le *Guide de référence du programmeur OLE DB* dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Si l'objet source de données est initialisé, les propriétés doivent appartenir au groupe de propriétés Source de données.  Si la même propriété est spécifiée plusieurs fois dans `pPropset`, la valeur utilisée varie en fonction du fournisseur.  Si `ulPropSets` est égal à zéro, ce paramètre est ignoré.  
  
 `ulPropSets`  
 \[in\] Nombre de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) passées dans l'argument *pPropSet*.  Si la valeur est égale à zéro, le fournisseur ignore `pPropset`.  
  
## Valeur de retour  
 `HRESULT` standard.  
  
## Notes  
 Cette méthode ouvre un objet source de données à l'aide des composants de service d'oledb32.dll ; cette DLL contient l'implémentation des fonctionnalités Composants de service, telles que la mise en pool de ressources, l'inscription de transaction automatique, etc.  Pour plus d'informations, consultez « Services OLE DB » dans le Guide de référence du programmeur OLE DB à l'adresse [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDataSource, classe](../../data/oledb/cdatasource-class.md)