---
title: "CMFCTasksPaneTaskGroup Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTasksPaneTaskGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTaskGroup class"
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
caps.latest.revision: 33
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 35
---
# CMFCTasksPaneTaskGroup Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCTasksPaneTaskGroup` est une classe d'assistance utilisée par le contrôle de [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) .  Les objets de type `CMFCTasksPaneTaskGroup` représentent *un groupe de tâches*.  Le groupe de tâches est une liste d'éléments que l'infrastructure affiche dans une zone séparé qui a un bouton de réduction.  La zone peut avoir une légende facultative \(nom de groupe\).  Si un groupe est réduit, la liste de tâches n'est pas visible.  
  
## Syntaxe  
  
```  
class CMFCTasksPaneTaskGroup : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup](../Topic/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup.md)|Construit un objet `CMFCTasksPaneTaskGroup`.|  
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTaskGroup::SetACCData](../Topic/CMFCTasksPaneTaskGroup::SetACCData.md)|Détermine les données d'accessibilité pour le groupe de tâches en cours.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTaskGroup::m\_bIsBottom](../Topic/CMFCTasksPaneTaskGroup::m_bIsBottom.md)|Détermine si le groupe de tâches est aligné en bas du contrôle de volet de tâches.|  
|[CMFCTasksPaneTaskGroup::m\_bIsCollapsed](../Topic/CMFCTasksPaneTaskGroup::m_bIsCollapsed.md)|Détermine si le groupe de tâches est réduit.|  
|[CMFCTasksPaneTaskGroup::m\_bIsSpecial](../Topic/CMFCTasksPaneTaskGroup::m_bIsSpecial.md)|Détermine si le groupe de tâches est *spécial.* L'infrastructure affiche les légendes particulières dans une couleur différente.|  
|[CMFCTasksPaneTaskGroup::m\_lstTasks](../Topic/CMFCTasksPaneTaskGroup::m_lstTasks.md)|Contient la liste interne de tâches.|  
|[CMFCTasksPaneTaskGroup::m\_rect](../Topic/CMFCTasksPaneTaskGroup::m_rect.md)|Spécifie le rectangle englobant de la légende de groupe.|  
|[CMFCTasksPaneTaskGroup::m\_rectGroup](../Topic/CMFCTasksPaneTaskGroup::m_rectGroup.md)|Spécifie le rectangle englobant du groupe.|  
|[CMFCTasksPaneTaskGroup::m\_strName](../Topic/CMFCTasksPaneTaskGroup::m_strName.md)|Spécifie le nom du groupe.|  
  
## Notes  
 l'illustration suivante montre un groupe de tâches développé :  
  
 ![Groupe de tâches, développé](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
 l'illustration suivante montre un groupe de tâches réduit :  
  
 ![Groupe de tâches réduit](../../mfc/reference/media/nexttaskgrpcollapse.png "NextTaskGrpCollapse")  
  
 l'illustration suivante montre un groupe de tâches sans légende :  
  
 ![Groupe de tâches sans légende](../../mfc/reference/media/nexttaskgrpnocapt.png "NextTaskGrpNoCapt")  
  
 l'illustration suivante montre les groupes à deux tâches.  Le premier groupe de tâches est marqué comme special en définissant l'indicateur d' `m_bIsSpecial` à `TRUE`, tandis que le second groupe de tâches n'est pas spécial.  Notez comment la légende pour le premier groupe de tâches est plus sombre que le deuxième groupe de tâches :  
  
 ![Groupe de tâches spéciales](../../mfc/reference/media/nexttaskgrpspecial.png "NextTaskGrpSpecial")  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)  
  
## Configuration requise  
 **en\-tête :** afxTasksPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md)   
 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)