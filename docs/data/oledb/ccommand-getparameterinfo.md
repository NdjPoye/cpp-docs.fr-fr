---
title: "CCommand::GetParameterInfo | Microsoft Docs"
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
  - "GetParameterInfo"
  - "CCommand.GetParameterInfo"
  - "CCommand::GetParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParameterInfo (méthode)"
ms.assetid: 9cd9277f-0161-4bd8-ad24-58e5e90b92a7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::GetParameterInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient une liste des paramètres de commande, du nom, et leurs types.  
  
## Syntaxe  
  
```  
  
      HRESULT CCommandBase::GetParameterInfo(  
   DB_UPARAMS* pParams,  
   DBPARAMINFO** ppParamInfo,  
   OLECHAR** ppNamesBuffer   
) throw ( );  
```  
  
#### Paramètres  
 Pour plus d'informations sur les curseurs, consultez le [Guide de référence du programmeur OLE DB](https://msdn.microsoft.com/en-us/library/ms714917.aspx) du .  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)