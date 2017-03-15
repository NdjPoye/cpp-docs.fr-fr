---
title: "IRowsetCreatorImpl::SetSite | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetCreatorImpl.SetSite"
  - "IRowsetCreatorImpl<T>::SetSite"
  - "IRowsetCreatorImpl::SetSite"
  - "SetSite"
  - "ATL.IRowsetCreatorImpl.SetSite"
  - "ATL::IRowsetCreatorImpl<T>::SetSite"
  - "ATL::IRowsetCreatorImpl::SetSite"
  - "ATL.IRowsetCreatorImpl<T>.SetSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetSite (méthode)"
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetCreatorImpl::SetSite
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le site contenant l'objet d'ensemble de lignes.  Pour plus d'informations, consultez l'[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
## Syntaxe  
  
```  
  
      STDMETHOD( SetSite )(  
   IUnknown* pCreator   
);  
```  
  
#### Paramètres  
 `pCreator`  
 \[in\] pointeur vers le pointeur d'interface de **IUnknown** du site qui gère l'objet d'ensemble de lignes.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 En outre, `IRowsetCreatorImpl::SetSite` active les propriétés OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetCreatorImpl, classe](../../data/oledb/irowsetcreatorimpl-class.md)