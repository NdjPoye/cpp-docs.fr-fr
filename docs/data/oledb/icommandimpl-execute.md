---
title: "ICommandImpl::Execute | Microsoft Docs"
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
  - "ICommandImpl::Execute"
  - "ICommandImpl.Execute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Execute (méthode)"
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::Execute
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute la commande.  
  
## Syntaxe  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### Paramètres  
 Consultez [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Notes  
 L'interface sortante demandée est une interface acquise de l'objet d'ensemble de lignes que cette fonction crée.  
  
 **Execute** appelle [CreateRowset](../../data/oledb/icommandimpl-createrowset.md).  Remplacer l'implémentation par défaut pour créer plusieurs jeux de lignes ou fournir vos propres conditions pour créer des ensembles de lignes.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [ICommandImpl, classe](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)