---
title: "CMFCTasksPaneTask Class | Microsoft Docs"
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
  - "CMFCTasksPaneTask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTasksPaneTask class"
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCTasksPaneTask Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CMFCTasksPaneTask` est une classe d'assistance qui représente des tâches pour le contrôle de volet de tâches \([CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)\).  l'objet de tâche représente un élément au groupe de tâches \([CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)\).  Chaque tâche peut avoir une commande que l'infrastructure exécute lorsqu'un utilisateur clique sur la tâche et une icône qui apparaît à gauche du nom de la tâche.  
  
## Syntaxe  
  
```  
class CMFCTasksPaneTask : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTask::CMFCTasksPaneTask](../Topic/CMFCTasksPaneTask::CMFCTasksPaneTask.md)|Crée et initialise un objet `CMFCTasksPaneTask`.|  
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTask::SetACCData](../Topic/CMFCTasksPaneTask::SetACCData.md)|Détermine les données d'accessibilité pour la tâche actuelle.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCTasksPaneTask::m\_bAutoDestroyWindow](../Topic/CMFCTasksPaneTask::m_bAutoDestroyWindow.md)|Détermine si la fenêtre de tâche est automatiquement perdue.|  
|[CMFCTasksPaneTask::m\_bIsBold](../Topic/CMFCTasksPaneTask::m_bIsBold.md)|Détermine si l'infrastructure dessine une étiquette de tâche en gras.|  
|[CMFCTasksPaneTask::m\_dwUserData](../Topic/CMFCTasksPaneTask::m_dwUserData.md)|Contient des données définies par l'utilisateur que l'infrastructure associe à la tâche.  Affectez à zéro si la tâche n'a pas de données associées.|  
|[CMFCTasksPaneTask::m\_hwndTask](../Topic/CMFCTasksPaneTask::m_hwndTask.md)|Un handle dans la fenêtre de tâche.|  
|[CMFCTasksPaneTask::m\_nIcon](../Topic/CMFCTasksPaneTask::m_nIcon.md)|L'index dans la liste d'images de l'image que l'infrastructure affiche en regard de la tâche.|  
|[CMFCTasksPaneTask::m\_nWindowHeight](../Topic/CMFCTasksPaneTask::m_nWindowHeight.md)|La hauteur de la fenêtre de tâche.  Si la tâche n'a pas de fenêtre de tâche, cette valeur est zéro.|  
|[CMFCTasksPaneTask::m\_pGroup](../Topic/CMFCTasksPaneTask::m_pGroup.md)|Un pointeur vers `CMFCTasksPaneTaskGroup` que cette tâche appartient.|  
|[CMFCTasksPaneTask::m\_rect](../Topic/CMFCTasksPaneTask::m_rect.md)|Spécifie le rectangle englobant de la tâche.|  
|[CMFCTasksPaneTask::m\_strName](../Topic/CMFCTasksPaneTask::m_strName.md)|Nom de la tâche.|  
|[CMFCTasksPaneTask::m\_uiCommandID](../Topic/CMFCTasksPaneTask::m_uiCommandID.md)|Spécifie l'ID de la commande que l'infrastructure exécute lorsque l'utilisateur clique sur la tâche.  Si cette valeur n'est pas un ID de commande valide, la tâche est traitée comme une étiquette simple.|  
  
## Notes  
 l'illustration suivante montre un groupe de tâches qui contient trois tâches :  
  
 ![Groupe de tâches, développé](../../mfc/reference/media/nexttaskgrpexpand.png "NextTaskGrpExpand")  
  
> [!NOTE]
>  Si une tâche n'a pas d'ID de commande valide, elle est traitée comme une étiquette simple.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)  
  
## Configuration requise  
 **en\-tête :** afxTasksPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)