---
title: "Classe CAnimationGroup | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationGroup"
  - "CAnimationGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationGroup (classe)"
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Classe CAnimationGroup
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente un groupe d'animation, qui combine un storyboard de l'animation, des objets et des transitions d'animation pour définir une animation.  
  
## Syntaxe  
  
```  
class CAnimationGroup;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationGroup::CAnimationGroup](../Topic/CAnimationGroup::CAnimationGroup.md)|Construit un groupe d'animation.|  
|[CAnimationGroup::~CAnimationGroup](../Topic/CAnimationGroup::~CAnimationGroup.md)|Le destructeur.  Appelé lorsqu'un groupe d'animation est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationGroup::Animate](../Topic/CAnimationGroup::Animate.md)|Anime un groupe.|  
|[CAnimationGroup::ApplyTransitions](../Topic/CAnimationGroup::ApplyTransitions.md)|Applique des transitions aux objets d'animation.|  
|[CAnimationGroup::FindAnimationObject](../Topic/CAnimationGroup::FindAnimationObject.md)|Recherche un objet d'animation qui contient la variable d'animation spécifiée.|  
|[CAnimationGroup::GetGroupID](../Topic/CAnimationGroup::GetGroupID.md)|Retourne GroupID.|  
|[CAnimationGroup::RemoveKeyframes](../Topic/CAnimationGroup::RemoveKeyframes.md)|Supprime et, éventuellement détruit, toutes les images clés qui appartiennent à un groupe d'animation.|  
|[CAnimationGroup::RemoveTransitions](../Topic/CAnimationGroup::RemoveTransitions.md)|Supprime les transitions des objets d'animation qui appartiennent à un groupe d'animation.|  
|[CAnimationGroup::Schedule](../Topic/CAnimationGroup::Schedule.md)|Planifie une animation à l'heure spécifiée.|  
|[CAnimationGroup::SetAutodestroyTransitions](../Topic/CAnimationGroup::SetAutodestroyTransitions.md)|Dirige tous les objet d'animation qui appartiennent au groupe et détruit automatiquement les transitions.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationGroup::AddKeyframes](../Topic/CAnimationGroup::AddKeyframes.md)|Programme d'assistance qui ajoute des images clés à un storyboard.|  
|[CAnimationGroup::AddTransitions](../Topic/CAnimationGroup::AddTransitions.md)|Programme d'assistance qui ajoute des transitions à un storyboard.|  
|[CAnimationGroup::CreateTransitions](../Topic/CAnimationGroup::CreateTransitions.md)|Programme d'assistance qui crée des objets de transition COM.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationGroup::m\_bAutoclearTransitions](../Topic/CAnimationGroup::m_bAutoclearTransitions.md)|Spécifie comment effacer les transitions des objet d'animation qui appartiennent au groupe.  Si ce membre a la valeur TRUE, les transitions sont supprimées automatiquement lorsqu'une animation a été planifiée.  Sinon, vous devez supprimer les transitions manuellement.|  
|[CAnimationGroup::m\_bAutodestroyAnimationObjects](../Topic/CAnimationGroup::m_bAutodestroyAnimationObjects.md)|Spécifie comment détruire les objets d'animation.  Si ce paramètre a la valeur TRUE, les objets d'animation seront détruits automatiquement lorsque le groupe est détruit.  Sinon, les objet d'animation doivent être détruits manuellement.  La valeur par défaut est FALSE.  Affectez TRUE uniquement cette valeur si tous les objets d'animation qui appartiennent au groupe sont alloués dynamiquement avec l'opérateur new.|  
|[CAnimationGroup::m\_bAutodestroyKeyframes](../Topic/CAnimationGroup::m_bAutodestroyKeyframes.md)|Indique comment détruire les images clés.  Si cette valeur est TRUE, tous les images clés sont supprimées et détruites ; sinon, elles sont supprimées uniquement de la liste.  La valeur par défaut est TRUE.|  
|[CAnimationGroup::m\_lstAnimationObjects](../Topic/CAnimationGroup::m_lstAnimationObjects.md)|Contient une liste d'objets d'animation.|  
|[CAnimationGroup::m\_lstKeyFrames](../Topic/CAnimationGroup::m_lstKeyFrames.md)|Contient une liste d'images clés.|  
|[CAnimationGroup::m\_pStoryboard](../Topic/CAnimationGroup::m_pStoryboard.md)|Pointe vers le storyboard de l'animation.  Ce pointeur est uniquement valide après l'appel d'Animate.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationGroup::m\_nGroupID](../Topic/CAnimationGroup::m_nGroupID.md)|Identificateur unique de groupe d'animation.|  
|[CAnimationGroup::m\_pParentController](../Topic/CAnimationGroup::m_pParentController.md)|Pointeur vers le contrôleur de l'animation auquel appartient ce groupe.|  
  
## Notes  
 Les groupes d'animation sont créés automatiquement par le contrôleur de l'animation \(CAnimationController\) lorsque vous ajoutez des objets d'animation à l'aide de CAnimationController::AddAnimationObject.  Un groupe d'animation est identifié par GroupID qui est généralement considéré comme un paramètre pour manipuler des groupes d'animation.  GroupID est pris du premier objet d'animation qui est ajouté à un nouveau groupe d'animation.  Un storyboard de l'animation encapsulée est créée après l'appel de CAnimationController::AnimateGroup et est accessible via m\_pStoryboard du membre public.  
  
## Hiérarchie d'héritage  
 [CAnimationGroup](../../mfc/reference/canimationgroup-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)