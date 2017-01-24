---
title: "CDynamicParameterAccessor::CDynamicParameterAccessor | Microsoft Docs"
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
  - "CDynamicParameterAccessor::CDynamicParameterAccessor"
  - "CDynamicParameterAccessor.CDynamicParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicParameterAccessor (classe), constructeur"
  - "CDynamicParameterAccessor (méthode)"
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::CDynamicParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Constructeur.  
  
## Syntaxe  
  
```  
  
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor( eBlobHandling, nBlobSize )  
```  
  
#### Paramètres  
 `eBlobHandling`  
 Spécifie comment les données BLOB doivent être gérée.  La valeur par défaut est **DBBLOBHANDLING\_DEFAULT**.  Voir le [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) pour obtenir une description des valeurs de **DBBLOBHANDLINGENUM**.  
  
 `nBlobSize`  
 La taille maximale du BLOB en octets ; les données de la colonne à cette valeur sont traitées en tant que BLOB.  La valeur par défaut est 8,000.  Voir le [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) pour plus d'informations.  
  
## Notes  
 Consultez le constructeur de [CDynamicAccessor::CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) pour plus d'informations sur la gestion des objets BLOB.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)