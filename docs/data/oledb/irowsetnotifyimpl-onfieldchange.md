---
title: "IRowsetNotifyImpl::OnFieldChange | Microsoft Docs"
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
  - "IRowsetNotifyImpl.OnFieldChange"
  - "IRowsetNotifyImpl::OnFieldChange"
  - "OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnFieldChange (méthode)"
ms.assetid: f26b492c-c86e-423b-9374-175e510a2860
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyImpl::OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Notifie le consommateur de toute modification apportée à la valeur d'une colonne.  
  
## Syntaxe  
  
```  
  
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### Paramètres  
 Voir [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) pour obtenir une description du paramètre.  
  
## Valeur de retour  
 Voir [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) pour obtenir une description de la valeur de retour.  
  
## Notes  
 Cette méthode inclut la méthode [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx).  Consultez la description de cette méthode dans le guide de référence du programmeur OLE DB pour plus d'informations.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [IRowsetNotifyImpl, classe](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)