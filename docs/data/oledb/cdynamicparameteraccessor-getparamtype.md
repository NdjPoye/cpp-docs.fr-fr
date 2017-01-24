---
title: "CDynamicParameterAccessor::GetParamType | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamType"
  - "CDynamicParameterAccessor:GetParamType"
  - "CDynamicParameterAccessor::GetParamType"
  - "ATL.CDynamicParameterAccessor.GetParamType"
  - "GetParamType"
  - "ATL::CDynamicParameterAccessor::GetParamType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamType (méthode)"
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le type de données d'un paramètre spécifique.  
  
## Syntaxe  
  
```  
  
      bool GetParamType(  
   DBORDINAL nParam,  
   DBTYPE* pType   
) const throw( );  
```  
  
#### Paramètres  
 `nParam`  
 \[in\] Le nombre du paramètre \(décalage de 1\).  Le paramètre 0 est réservé pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 `pType`  
 \[out\] Un pointeur à la variable qui contient le type de données du paramètre spécifié.  
  
## Valeur de retour  
 Retourne la valeur **vrai** en cas de réussite, ou de **faux** en cas d'échec.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)