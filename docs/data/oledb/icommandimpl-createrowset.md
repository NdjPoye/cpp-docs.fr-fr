---
title: "ICommandImpl::CreateRowset | Microsoft Docs"
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
  - "ICommandImpl::CreateRowset"
  - "ICommandImpl.CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset (méthode)"
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelé par [Exécuter](../../data/oledb/icommandimpl-execute.md) pour créer un ensemble de lignes unique.  
  
## Syntaxe  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### Paramètres  
 `RowsetClass`  
 Un membre de la classe de modèle qui représente la classe d'ensemble de l'utilisateur.  Généralement généré par l'Assistant.  
  
 `pUnkOuter`  
 \[in\] pointeur à l'interface de contrôle de **IInconnu** si l'ensemble de lignes est créé dans le cadre d'un agrégat ; sinon, la valeur est NULL.  
  
 `riid`  
 \[in\] correspond à `riid` dans `ICommand::Execute`.  
  
 `pParams`  
 \[In\/out\] correspond à `pParams` dans `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Correspond à `pcRowsAffected` in `ICommand::Execute`.  
  
 `ppRowset`  
 \[In\/out\] correspond à `ppRowset` dans `ICommand::Execute`.  
  
 `pRowsetObj`  
 \[out\] pointeur à un objet d'ensemble de lignes.  Généralement ce paramètre n'est pas utilisé, mais il peut être utilisé si vous devez effectuer des tâches dans l'ensemble de lignes avant de le passer à un objet COM.  La durée de vie de `pRowsetObj` est liée par `ppRowset`.  
  
## Valeur de retour  
 Une valeur standard `HRESULT`.  Pour obtenir la liste des valeurs typiques, consultez `ICommand::Execute`.  
  
## Notes  
 Pour créer plusieurs jeux de lignes, ou fournir vos propres conditions pour créer des ensembles de lignes, placez des appels à `CreateRowset` de **Exécuter**.  
  
 Consultez [ICommande::Executer](https://msdn.microsoft.com/en-us/library/ms718095.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [ICommandImpl, classe](../../data/oledb/icommandimpl-class.md)