---
title: ICommandTextImpl::GetCommandText | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
dev_langs: C++
helpviewer_keywords: GetCommandText method
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b24afdf4bddd30ca2644edb1c7970a193251bdb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtextimplgetcommandtext"></a>ICommandTextImpl::GetCommandText
Retourne la commande de texte définie par le dernier appel à [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) dans les *de référence du programmeur OLE DB*. Le *pguidDialect* paramètre est ignoré par défaut.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [ICommandTextImpl, classe](../../data/oledb/icommandtextimpl-class.md)