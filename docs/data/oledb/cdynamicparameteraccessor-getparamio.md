---
title: "CDynamicParameterAccessor::GetParamIO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetParamIO"
  - "CDynamicParameterAccessor::GetParamIO"
  - "ATL.CDynamicParameterAccessor.GetParamIO"
  - "CDynamicParameterAccessor.GetParamIO"
  - "ATL::CDynamicParameterAccessor::GetParamIO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamIO (méthode)"
ms.assetid: 9c485e39-c67e-4df7-a707-c773019c4d1e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::GetParamIO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si le paramètre est un paramètre d'entrée ou de sortie.  
  
## Syntaxe  
  
```  
  
      bool GetParamIO(   
   DBORDINAL nParam,   
   DBPARAMIO * pParamIO    
) const throw( );  
```  
  
#### Paramètres  
 `nParam`  
 \[in\] Le nombre de paramètres \(décalage de 1\).  Le paramètre 0 est réservée pour les valeurs de retour.  Le numéro de paramètre représente l'index du paramètre en fonction de son ordre dans l'appel SQL ou celui d'une procédure stockée.  Consultez [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) pour obtenir un exemple.  
  
 *pParamIO*  
 Pointeur vers une variable qui contient le type de **DBPARAMIO** \(entrée ou sortie\) du paramètre.  Cette ligne est définie de la manière suivante :  
  
 `typedef DWORD DBPARAMIO;`  
  
 `enum DBPARAMIOENUM`  
  
 `{   DBPARAMIO_NOTPARAM   = 0,`  
  
 `DBPARAMIO_INPUT      = 0x1,`  
  
 `DBPARAMIO_OUTPUT     = 0x2`  
  
 `};`  
  
## Valeur de retour  
 Retourne la valeur **vrai** en cas de réussite, **false** en cas d'échec.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)