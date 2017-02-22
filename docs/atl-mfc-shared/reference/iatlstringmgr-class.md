---
title: "IAtlStringMgr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAtlStringMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlStringMgr class"
  - "mémoire, gérer"
  - "shared classes, IAtlStringMgr"
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# IAtlStringMgr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe représente l'interface à un gestionnaire de mémoire d' `CStringT` .  
  
## Syntaxe  
  
```  
  
__interface IAtlStringMgr  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Allouez](../Topic/IAtlStringMgr::Allocate.md)|Appelez cette méthode pour allouer une nouvelle structure de données de type chaîne.|  
|[Clone](../Topic/IAtlStringMgr::Clone.md)|Appelez cette méthode pour retourner un pointeur vers un nouveau gestionnaire de chaînes à utiliser avec une autre instance d' `CSimpleStringT`.|  
|[Free \(libre\)](../Topic/IAtlStringMgr::Free.md)|Appelez cette méthode pour libérer une structure de données de type chaîne.|  
|[GetNilString](../Topic/IAtlStringMgr::GetNilString.md)|Retourne un pointeur vers l'objet d' `CStringData` utilisé par les objets de chaîne vide.|  
|[Réaffectez](../Topic/IAtlStringMgr::Reallocate.md)|Appelez cette méthode pour réaffecter une structure de données de type chaîne.|  
  
## Notes  
 Cette interface gère la mémoire utilisée par les classes par MFC indépendantes de chaîne ; par exemple [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), et [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Vous pouvez également utiliser cette classe pour implémenter un gestionnaire de mémoire personnalisé pour votre classe personnalisée de chaîne.  Pour plus d'informations, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## Configuration requise  
 **Header:** atlsimpstr.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)