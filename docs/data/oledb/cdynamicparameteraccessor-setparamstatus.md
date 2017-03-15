---
title: "CDynamicParameterAccessor::SetParamStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::SetParamStatus"
  - "ATL.CDynamicParameterAccessor.SetParamStatus"
  - "ATL::CDynamicParameterAccessor::SetParamStatus"
  - "CDynamicParameterAccessor.SetParamStatus"
  - "SetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamStatus (méthode)"
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l'état du paramètre stocké en mémoire tampon.  
  
## Syntaxe  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### Paramètres  
 `nParam`  
 \[in\] Le nombre de paramètres \(décalage de 1\).  Le paramètre 0 est réservé pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 *status*  
 \[in\] L'état `DBSTATUS` du paramètre spécifié.  Pour plus d'informations sur les valeurs de `DBSTATUS`, consultez l' [État](https://msdn.microsoft.com/en-us/library/ms722617.aspx) dans *OLE DB guide de référence du programmeur*, ou recherchez dans `DBSTATUS` oledb.h.  
  
## Notes  
 Retourne la valeur **vrai** en cas de réussite, **false** en cas d'échec.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)