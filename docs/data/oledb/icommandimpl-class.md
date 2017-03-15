---
title: "ICommandImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandImpl (classe)"
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit l'implémentation de l'interface d'[ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx).  
  
## Syntaxe  
  
```  
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `ICommandImpl`.  
  
 `CommandBase`  
 Interface de commande.  La valeur par défaut est `ICommand`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Annule l'exécution de la commande actuelle.|  
|[Annuler](../../data/oledb/icommandimpl-cancel.md)|Annule l'exécution de la commande actuelle.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Crée un objet d'un ensemble de lignes.|  
|[Execute](../../data/oledb/icommandimpl-execute.md)|Exécute la commande.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Retourne un pointeur d'interface sur la session qui a créé la commande.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|Constructeur.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Indique si la commande doit être annulée.|  
|[m\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Indique si la commande peut être annulée lors de l'exécution.|  
|[m\_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Indique si la commande est actuellement en cours d'exécution.|  
  
## Notes  
 Interface obligatoire sur l'objet de commande.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)