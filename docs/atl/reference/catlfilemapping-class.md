---
title: "CAtlFileMapping Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlFileMapping<T>"
  - "ATL.CAtlFileMapping"
  - "ATL::CAtlFileMapping"
  - "CAtlFileMapping"
  - "ATL.CAtlFileMapping<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMapping class"
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFileMapping Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente un fichier mappé en mémoire, en ajoutant un opérateur de cast aux méthodes de [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
typename T= char  
>  
class CAtlFileMapping :  
public CAtlFileMappingBase  
```  
  
#### Paramètres  
 `T`  
 Le type de données utilisé pour l'opérateur de cast.  
  
## Membres  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlFileMapping::operator T\*](../Topic/CAtlFileMapping::operator%20T*.md)|Permet la conversion implicite des objets d' `CAtlFileMapping` à `T`**\***.|  
  
## Notes  
 Cette classe ajoute un opérateur de cast unique pour activer la conversion implicite des objets d' `CAtlFileMapping` à `T`**\***.  D'autres membres fournis par la classe de base, [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## Hiérarchie d'héritage  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## Configuration requise  
 **Header:** atlfile.h  
  
## Voir aussi  
 [CAtlFileMappingBase Class](../../atl/reference/catlfilemappingbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)