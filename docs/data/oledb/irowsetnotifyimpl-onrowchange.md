---
title: "IRowsetNotifyImpl::OnRowChange | Microsoft Docs"
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
  - "IRowsetNotifyImpl::OnRowChange"
  - "IRowsetNotifyImpl.OnRowChange"
  - "OnRowChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnRowChange (méthode)"
ms.assetid: 148bee03-3707-4bbf-8c51-657efc63645f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyImpl::OnRowChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Notifie le consommateur de la première modification apportée à une ligne ou de toute modification qui affecte la ligne entière.  
  
## Syntaxe  
  
```  
  
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### Paramètres  
 Voir [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) pour obtenir une description du paramètre.  
  
## Valeur de retour  
 Voir [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) pour obtenir une description de la valeur de retour.  
  
## Notes  
 Cette méthode inclut la méthode [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx).  Consultez la description de cette méthode dans le guide de référence du programmeur OLE DB pour plus d'informations.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [IRowsetNotifyImpl, classe](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)