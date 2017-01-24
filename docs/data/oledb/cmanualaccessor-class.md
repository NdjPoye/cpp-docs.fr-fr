---
title: "CManualAccessor, classe | Microsoft Docs"
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
  - "ATL::CManualAccessor"
  - "ATL.CManualAccessor"
  - "CManualAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CManualAccessor (classe)"
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CManualAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un type d'accesseur destiné aux utilisateurs expérimentés.  
  
## Syntaxe  
  
```  
class CManualAccessor : public CAccessorBase  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AjoutEntreeLien](../../data/oledb/cmanualaccessor-addbindentry.md)|Ajoute une entrée de lien aux colonnes de sortie.|  
|[AjoutParametreEntree](../../data/oledb/cmanualaccessor-addparameterentry.md)|Ajoute une entrée de paramètre de l'accesseur de paramètre.|  
|[CreerAccesseur](../../data/oledb/cmanualaccessor-createaccessor.md)|Attribue la mémoire pour les structures de colonnes de lien et initialise les colonnes des données des membres.|  
|[CreerParametreAccesseur](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Attribue la mémoire pour les structures de paramètres liés et initialise les paramètres des données des membres.|  
  
## Notes  
 Utilisation `CManualAccessor`, vous pouvez spécifier la liaison selon les colonnes et de paramètres de sortie des appels de fonction CLR.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor, classe](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)