---
title: "CJumpList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxadv/CJumpList"
  - "CJumpList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CJumpList class"
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CJumpList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CJumpList` est la liste des raccourcis indiquée lorsque vous cliquez avec le bouton droit sur une icône dans la barre des tâches.  
  
## Syntaxe  
  
```  
class CJumpList;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CJumpList::CJumpList](../Topic/CJumpList::CJumpList.md)|Construit un objet `CJumpList`.|  
|[CJumpList::~CJumpList](../Topic/CJumpList::~CJumpList.md)|Détruit un objet `CJumpList`.|  
  
|Nom|Description|  
|---------|-----------------|  
|[CJumpList::AbortList](../Topic/CJumpList::AbortList.md)|Interrompt une transaction de génération de liste sans valider.|  
|[CJumpList::AddDestination](../Topic/CJumpList::AddDestination.md)|Surchargé.  Ajoute la destination à la liste.|  
|[CJumpList::AddKnownCategory](../Topic/CJumpList::AddKnownCategory.md)|Ajoute une catégorie à la liste.|  
|[CJumpList::AddTask](../Topic/CJumpList::AddTask.md)|Surchargé.  Ajoute des éléments à la catégorie canonique de tâches.|  
|[CJumpList::AddTasks](../Topic/CJumpList::AddTasks.md)|Ajoute des éléments à la catégorie canonique de tâches.|  
|[CJumpList::AddTaskSeparator](../Topic/CJumpList::AddTaskSeparator.md)|Ajoute un séparateur entre des tâches.|  
|[CJumpList::ClearAll](../Topic/CJumpList::ClearAll.md)|Supprime toutes les tâches et destinations ajoutées à l'instance actuelle d' `CJumpList` jusqu'à présent.|  
|[CJumpList::ClearAllDestinations](../Topic/CJumpList::ClearAllDestinations.md)|Supprime toutes les destinations ajoutées à l'instance actuelle d' `CJumpList` jusqu'à présent.|  
|[CJumpList::CommitList](../Topic/CJumpList::CommitList.md)|Termine une transaction d'une liste génération et investit la liste stocké dans la mémoire associée \(le Registre dans ce cas.\)|  
|[CJumpList::GetDestinationList](../Topic/CJumpList::GetDestinationList.md)|Extrait un pointeur d'interface vers la liste de destination.|  
|[CJumpList::GetMaxSlots](../Topic/CJumpList::GetMaxSlots.md)|Récupère le nombre maximal d'éléments, notamment les en\-têtes de catégorie qui peuvent afficher dans le menu de la destination de l'application appelante.|  
|[CJumpList::GetRemovedItems](../Topic/CJumpList::GetRemovedItems.md)|Tableau de retour d'éléments qui représentent des destinations supprimées.|  
|[CJumpList::InitializeList](../Topic/CJumpList::InitializeList.md)|Commence une transaction d'une liste génération.|  
|[CJumpList::SetAppID](../Topic/CJumpList::SetAppID.md)|Définit l'ID de modèle utilisateur d'application pour la liste qui sera générée.|  
  
## Hiérarchie d'héritage  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## Configuration requise  
 **en\-tête :** afxadv.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)