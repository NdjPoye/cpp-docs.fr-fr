---
title: "ICommandTextImpl::GetCommandText | Microsoft Docs"
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
  - "GetCommandText"
  - "ICommandTextImpl.GetCommandText"
  - "ICommandTextImpl::GetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandText (méthode)"
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl::GetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la commande de texte définie par le dernier appel à [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
## Syntaxe  
  
```  
  
      STDMETHOD(GetCommandText)(   
   GUID * pguidDialect,   
   LPOLESTR * ppwszCommand    
);  
```  
  
#### Paramètres  
 Consultez le [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) dans le *Guide de référence du programmeur OLE DB*.  Le paramètre *pguidDialect* est ignoré par défaut.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [ICommandTextImpl, classe](../../data/oledb/icommandtextimpl-class.md)