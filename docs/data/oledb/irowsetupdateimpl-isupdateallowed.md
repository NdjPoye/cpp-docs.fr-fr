---
title: "IRowsetUpdateImpl::IsUpdateAllowed | Microsoft Docs"
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
  - "IRowsetUpdateImpl::IsUpdateAllowed"
  - "IRowsetUpdateImpl.IsUpdateAllowed"
  - "IsUpdateAllowed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsUpdateAllowed (méthode)"
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::IsUpdateAllowed
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Remplacez cette méthode pour vérifier la sécurité, les contraintes, etc. avant les mises à jour.  
  
## Syntaxe  
  
```  
  
      HRESULT IsUpdateAllowed(  
   DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */  
);  
```  
  
#### Paramètres  
 *status*  
 \[in\] l'état des opérations en attente sur les lignes.  
  
 *hRowUpdate*  
 \[in\] Gestion des lignes que l'utilisateur souhaite mettre à jour.  
  
 *pRowStatus*  
 \[out\] L'état retourné à l'utilisateur.  
  
## Notes  
 Si vous constatez qu'une mise à jour doit être autorisée, retournez `S_OK`; sinon retournez **E\_FAIL**.  Si vous autorisez une mise à niveau, vous devez également définir **DBROWSTATUS** dans [IRowsetUpdateImpl::Update](../../data/oledb/irowsetupdateimpl-update.md) à [état de ligne](https://msdn.microsoft.com/en-us/library/ms722752.aspx)approprié.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetUpdateImpl, classe](../../data/oledb/irowsetupdateimpl-class.md)