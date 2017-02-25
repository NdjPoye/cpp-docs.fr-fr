---
title: "Classe CAnimationController | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationController"
  - "afxanimationcontroller/CAnimationController"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationController (classe)"
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Classe CAnimationController
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente le contrôleur de l'animation, qui propose une interface centrale pour créer et gérer des animations.  
  
## Syntaxe  
  
```  
class CAnimationController : public CObject;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationController::CAnimationController](../Topic/CAnimationController::CAnimationController.md)|Construit un contrôleur de l'animation.|  
|[CAnimationController::~CAnimationController](../Topic/CAnimationController::~CAnimationController.md)|Le destructeur.  Appelé lorsqu'un objet contrôleur de l'animation est détruit.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationController::AddAnimationObject](../Topic/CAnimationController::AddAnimationObject.md)|Ajoute un objet d'animation à un groupe qui appartient au contrôleur de l'animation.|  
|[CAnimationController::AddKeyframeToGroup](../Topic/CAnimationController::AddKeyframeToGroup.md)|Ajoute une image clé à un groupe.|  
|[CAnimationController::AnimateGroup](../Topic/CAnimationController::AnimateGroup.md)|Prépare un groupe pour exécuter l'animation et la planifie éventuellement.|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Surchargé.  Appelé par l'infrastructure pour nettoyer le groupe lorsque l'animation a été planifiée.|  
|[CAnimationController::CreateKeyframe](../Topic/CAnimationController::CreateKeyframe.md)|Surchargé.  Crée une image clé qui dépend de la transition et l'ajoute au groupe spécifié.|  
|[CAnimationController::EnableAnimationManagerEvent](../Topic/CAnimationController::EnableAnimationManagerEvent.md)|Définit ou libère un gestionnaire à appeler lorsque l'état du gestionnaire d'animations change.|  
|[CAnimationController::EnableAnimationTimerEventHandler](../Topic/CAnimationController::EnableAnimationTimerEventHandler.md)|Définit ou libère un gestionnaire pour les événements de minutage et un gestionnaire pour les mises à jour de minutage.|  
|[CAnimationController::EnablePriorityComparisonHandler](../Topic/CAnimationController::EnablePriorityComparisonHandler.md)|Définit ou libère le gestionnaire de comparaison de la priorité à appeler afin de déterminer si un storyboard planifié peut être annulé, terminé, tronqué ou compressé.|  
|[CAnimationController::EnableStoryboardEventHandler](../Topic/CAnimationController::EnableStoryboardEventHandler.md)|Définit ou libère un gestionnaire pour l'état du storyboard et les événements de mise à jour.|  
|[CAnimationController::FindAnimationGroup](../Topic/CAnimationController::FindAnimationGroup.md)|Surchargé.  Recherche un groupe d'animation en fonction de son storyboard.|  
|[CAnimationController::FindAnimationObject](../Topic/CAnimationController::FindAnimationObject.md)|Recherche l'objet d'animation contenant une variable d'animation spécifiée.|  
|[CAnimationController::GetKeyframeStoryboardStart](../Topic/CAnimationController::GetKeyframeStoryboardStart.md)|Retourne une image clé qui identifie le début du storyboard.|  
|[CAnimationController::GetUIAnimationManager](../Topic/CAnimationController::GetUIAnimationManager.md)|Fournit l'accès à l'objet IUIAnimationManager encapsulé.|  
|[CAnimationController::GetUIAnimationTimer](../Topic/CAnimationController::GetUIAnimationTimer.md)|Fournit l'accès à l'objet IUIAnimationTimer encapsulé.|  
|[CAnimationController::GetUITransitionFactory](../Topic/CAnimationController::GetUITransitionFactory.md)|Pointeur vers l'interface IUIAnimationTransitionFactory ou NULL, si la création de la bibliothèque de transitions a échoué.|  
|[CAnimationController::GetUITransitionLibrary](../Topic/CAnimationController::GetUITransitionLibrary.md)|Fournit l'accès à l'objet IUIAnimationTransitionLibrary encapsulé.|  
|[CAnimationController::IsAnimationInProgress](../Topic/CAnimationController::IsAnimationInProgress.md)|Indique si au moins un groupe joue l'animation.|  
|[CAnimationController::IsValid](../Topic/CAnimationController::IsValid.md)|Indique si le contrôleur de l'animation est valide.|  
|[CAnimationController::OnAnimationIntegerValueChanged](../Topic/CAnimationController::OnAnimationIntegerValueChanged.md)|Appelé par l'infrastructure lorsque la valeur entière de la variable d'animation a changé.|  
|[CAnimationController::OnAnimationManagerStatusChanged](../Topic/CAnimationController::OnAnimationManagerStatusChanged.md)|Appelé par l'infrastructure en réponse à un événement StatusChanged du gestionnaire d'animations.|  
|[CAnimationController::OnAnimationTimerPostUpdate](../Topic/CAnimationController::OnAnimationTimerPostUpdate.md)|Appelé par l'infrastructure à l'issue d'une mise à jour de l'animation.|  
|[CAnimationController::OnAnimationTimerPreUpdate](../Topic/CAnimationController::OnAnimationTimerPreUpdate.md)|Appelé par l'infrastructure avant le début d'une mise à jour de l'animation.|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](../Topic/CAnimationController::OnAnimationTimerRenderingTooSlow.md)|Appelé par l'infrastructure lorsque la fréquence d'images du rendu d'une animation passe sous le seuil minimum d'une fréquence d'images souhaité.|  
|[CAnimationController::OnAnimationValueChanged](../Topic/CAnimationController::OnAnimationValueChanged.md)|Appelé par l'infrastructure lorsque la valeur de la variable d'animation a changé.|  
|[CAnimationController::OnBeforeAnimationStart](../Topic/CAnimationController::OnBeforeAnimationStart.md)|Appelé par l'infrastructure juste avant que l'animation ne soit planifiée.|  
|[CAnimationController::OnHasPriorityCancel](../Topic/CAnimationController::OnHasPriorityCancel.md)|Appelé par l'infrastructure pour résoudre des conflits de planification.|  
|[CAnimationController::OnHasPriorityCompress](../Topic/CAnimationController::OnHasPriorityCompress.md)|Appelé par l'infrastructure pour résoudre des conflits de planification.|  
|[CAnimationController::OnHasPriorityConclude](../Topic/CAnimationController::OnHasPriorityConclude.md)|Appelé par l'infrastructure pour résoudre des conflits de planification.|  
|[CAnimationController::OnHasPriorityTrim](../Topic/CAnimationController::OnHasPriorityTrim.md)|Appelé par l'infrastructure pour résoudre des conflits de planification.|  
|[CAnimationController::OnStoryboardStatusChanged](../Topic/CAnimationController::OnStoryboardStatusChanged.md)|Appelé par l'infrastructure lorsque l'état du storyboard a changé.|  
|[CAnimationController::OnStoryboardUpdated](../Topic/CAnimationController::OnStoryboardUpdated.md)|Appelé par l'infrastructure lorsque le storyboard a été mise à jour.|  
|[CAnimationController::RemoveAllAnimationGroups](../Topic/CAnimationController::RemoveAllAnimationGroups.md)|Supprime tous les groupes d'animation du contrôleur de l'animation.|  
|[CAnimationController::RemoveAnimationGroup](../Topic/CAnimationController::RemoveAnimationGroup.md)|Supprime un groupe d'animation avec l'ID spécifié du contrôleur de l'animation.|  
|[CAnimationController::RemoveAnimationObject](../Topic/CAnimationController::RemoveAnimationObject.md)|Supprimez un objet d'animation du contrôleur de l'animation.|  
|[CAnimationController::RemoveTransitions](../Topic/CAnimationController::RemoveTransitions.md)|Supprime les transitions des objets d'animation qui appartiennent au groupe spécifié.|  
|[CAnimationController::ScheduleGroup](../Topic/CAnimationController::ScheduleGroup.md)|Planifie une animation.|  
|[CAnimationController::SetRelatedWnd](../Topic/CAnimationController::SetRelatedWnd.md)|Établit une relation entre le contrôleur de l'animation et une fenêtre.|  
|[CAnimationController::UpdateAnimationManager](../Topic/CAnimationController::UpdateAnimationManager.md)|Dirige le gestionnaire d'animations vers la mise  à jour des valeurs de toutes les variables d'animation.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|Surchargé.  Programme d'assistance qui nettoie le groupe.|  
|[CAnimationController::OnAfterSchedule](../Topic/CAnimationController::OnAfterSchedule.md)|Appelé par l'infrastructure lorsqu'une animation pour le groupe spécifié vient d'être planifiée.|  
  
### Données membres protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CAnimationController::g\_KeyframeStoryboardStart](../Topic/CAnimationController::g_KeyframeStoryboardStart.md)|Image clé qui représente le démarrage du storyboard.|  
|[CAnimationController::m\_bIsValid](../Topic/CAnimationController::m_bIsValid.md)|Indique si un contrôleur de l'animation est valide ou non.  Ce membre a la valeur FALSE si le système d'exploitation actuel ne prend pas en charge l'API Animation de Windows.|  
|[CAnimationController::m\_lstAnimationGroups](../Topic/CAnimationController::m_lstAnimationGroups.md)|Liste des groupes d'animation qui appartiennent à ce contrôleur de l'animation.|  
|[CAnimationController::m\_pAnimationManager](../Topic/CAnimationController::m_pAnimationManager.md)|Stocke un pointeur à l'objet COM du gestionnaire d'animation.|  
|[CAnimationController::m\_pAnimationTimer](../Topic/CAnimationController::m_pAnimationTimer.md)|Stocke un pointeur à l'objet COM du minuteur de l'animation.|  
|[CAnimationController::m\_pRelatedWnd](../Topic/CAnimationController::m_pRelatedWnd.md)|Pointeur vers un objet CWnd connexe qui peut être redessiné automatiquement lorsque l'état du gestionnaire d'animations change ou que l'événement de mise à jour postérieure se produit.  Peut être NULL.|  
|[CAnimationController::m\_pTransitionFactory](../Topic/CAnimationController::m_pTransitionFactory.md)|Stocke un pointeur à l'objet COM de la fabrique de transition.|  
|[CAnimationController::m\_pTransitionLibrary](../Topic/CAnimationController::m_pTransitionLibrary.md)|Stocke un pointeur à l'objet COM de la bibliothèque de transitions.|  
  
## Notes  
 La classe CAnimationController est la classe clé qui gère les animations.  Vous pouvez créer un ou plusieurs instances du contrôleur de l'animation dans une application et, éventuellement, connectez une instance du contrôleur de l'animation à un objet CWnd à l'aide de CAnimationController::SetRelatedWnd.  Cette connexion est requise pour envoyer automatiquement des messages WM\_PAINT à la fenêtre connexe lorsque l'état du gestionnaire d'animations change ou que la minuterie de l'animation est mise à jour.  Si vous n'activez pas cette relation, vous devez redessiner une fenêtre qui affiche une animation manuellement.  À cette fin, vous pouvez dériver une classe de CAnimationController et remplacer OnAnimationManagerStatusChanged et\/ou OnAnimationTimerPostUpdate et invalider une ou plusieurs fenêtres, si nécessaire.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationController](../../mfc/reference/canimationcontroller-class.md)  
  
## Configuration requise  
 **En\-tête :** afxanimationcontroller.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)