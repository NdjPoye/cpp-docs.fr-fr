---
title: "IRowsetChangeImpl::FlushData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetChangeImpl::FlushData"
  - "IRowsetChangeImpl.FlushData"
  - "FlushData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FlushData (méthode)"
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetChangeImpl::FlushData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Substitué par le fournisseur pour soumettre des données à son magasin.  
  
## Syntaxe  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### Paramètres  
 *hRowToFlush*  
 \[in\] Handle pour les lignes pour les données.  Le type de cette ligne dépend de l'argument TEMPLATE *de RowClass* de la classe `IRowsetImpl` \(`CSimpleRow` par défaut\).  
  
 *hAccessorToFlush*  
 \[in\] handle de l'accesseur, qui contient les informations de liaison et les informations de type dans son **PROVIDER\_MAP** \(voir [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)\).  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetChangeImpl Class](../../data/oledb/irowsetchangeimpl-class.md)