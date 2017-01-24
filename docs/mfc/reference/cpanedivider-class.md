---
title: "CPaneDivider Class | Microsoft Docs"
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
  - "CPaneDivider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDivider class"
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDivider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 La classe d' `CPaneDivider` divise deux volets, divise deux groupes de volets, ou sépare un groupe de volets de la zone cliente de la fenêtre frame principale.  
  
## Syntaxe  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneDivider::CPaneDivider](../Topic/CPaneDivider::CPaneDivider.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneDivider::AddPaneContainer](../Topic/CPaneDivider::AddPaneContainer.md)||  
|[CPaneDivider::AddPane](../Topic/CPaneDivider::AddPane.md)||  
|[CPaneDivider::AddRecentPane](../Topic/CPaneDivider::AddRecentPane.md)||  
|[CPaneDivider::CalcExpectedDockedRect](../Topic/CPaneDivider::CalcExpectedDockedRect.md)||  
|[CPaneDivider::CalcFixedLayout](../Topic/CPaneDivider::CalcFixedLayout.md)|\(Substitutions [CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md).\)|  
|[CPaneDivider::CheckVisibility](../Topic/CPaneDivider::CheckVisibility.md)||  
|[CPaneDivider::CreateEx](../Topic/CPaneDivider::CreateEx.md)|\(Substitutions [CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md).\)|  
|[CPaneDivider::DoesAllowDynInsertBefore](../Topic/CPaneDivider::DoesAllowDynInsertBefore.md)|\(Substitutions [CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md).\)|  
|[CPaneDivider::DoesContainFloatingPane](../Topic/CPaneDivider::DoesContainFloatingPane.md)||  
|[CPaneDivider::FindPaneContainer](../Topic/CPaneDivider::FindPaneContainer.md)||  
|[CPaneDivider::FindTabbedPane](../Topic/CPaneDivider::FindTabbedPane.md)||  
|[CPaneDivider::GetDefaultWidth](../Topic/CPaneDivider::GetDefaultWidth.md)||  
|[CPaneDivider::GetFirstPane](../Topic/CPaneDivider::GetFirstPane.md)||  
|[CPaneDivider::GetPaneDividerStyle](../Topic/CPaneDivider::GetPaneDividerStyle.md)||  
|[CPaneDivider::GetRootContainerRect](../Topic/CPaneDivider::GetRootContainerRect.md)||  
|[CPaneDivider::GetWidth](../Topic/CPaneDivider::GetWidth.md)||  
|[CPaneDivider::Init](../Topic/CPaneDivider::Init.md)||  
|[CPaneDivider::InsertPane](../Topic/CPaneDivider::InsertPane.md)||  
|[CPaneDivider::IsAutoHideMode](../Topic/CPaneDivider::IsAutoHideMode.md)|\(Substitutions [CBasePane::IsAutoHideMode](../Topic/CBasePane::IsAutoHideMode.md).\)|  
|[CPaneDivider::IsDefault](../Topic/CPaneDivider::IsDefault.md)||  
|[CPaneDivider::IsHorizontal](../Topic/CPaneDivider::IsHorizontal.md)|\(Substitutions [CBasePane::IsHorizontal](../Topic/CBasePane::IsHorizontal.md).\)|  
|[CPaneDivider::Move](../Topic/CPaneDivider::Move.md)||  
|[CPaneDivider::NotifyAboutRelease](../Topic/CPaneDivider::NotifyAboutRelease.md)||  
|[CPaneDivider::OnShowPane](../Topic/CPaneDivider::OnShowPane.md)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](../Topic/CPaneDivider::ReleaseEmptyPaneContainers.md)||  
|[CPaneDivider::RemovePane](../Topic/CPaneDivider::RemovePane.md)||  
|[CPaneDivider::ReplacePane](../Topic/CPaneDivider::ReplacePane.md)||  
|[CPaneDivider::RepositionPanes](../Topic/CPaneDivider::RepositionPanes.md)||  
|[CPaneDivider::Serialize](../Topic/CPaneDivider::Serialize.md)|\(Substitutions `CBasePane::Serialize`.\)|  
|[CPaneDivider::SetAutoHideMode](../Topic/CPaneDivider::SetAutoHideMode.md)||  
|[CPaneDivider::SetPaneContainerManager](../Topic/CPaneDivider::SetPaneContainerManager.md)||  
|[CPaneDivider::ShowWindow](../Topic/CPaneDivider::ShowWindow.md)||  
|[CPaneDivider::StoreRecentDockSiteInfo](../Topic/CPaneDivider::StoreRecentDockSiteInfo.md)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](../Topic/CPaneDivider::StoreRecentTabRelatedInfo.md)||  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneDivider::GetPanes](../Topic/CPaneDivider::GetPanes.md)|Retourne la liste des volets qui résident dans [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  Cette méthode doit être appelée uniquement pour les séparateurs par défaut de volet.|  
|[CPaneDivider::GetPaneDividers](../Topic/CPaneDivider::GetPaneDividers.md)|Retourne la liste des séparateurs de volet qui résident dans [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  Cette méthode doit être appelée uniquement pour les séparateurs par défaut de volet.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneDivider::m\_nDefaultWidth](../Topic/CPaneDivider::m_nDefaultWidth.md)|Spécifie la largeur par défaut en pixels de tous les séparateurs de volet de l'application.|  
|[CPaneDivider::m\_pSliderRTC](../Topic/CPaneDivider::m_pSliderRTC.md)|Contient un pointeur vers des informations de classe d'exécution sur `CPaneDivider`objet dérivé.|  
  
## Notes  
 L'infrastructure crée des objets d' `CPaneDivider` automatiquement lorsqu'un volet est ancré.  
  
 Il existe deux types de séparateurs de volet :  
  
-   un diviseur par défaut du volet est créé lorsqu'un groupe de volets est ancré à un côté de la fenêtre frame principale.  Le séparateur par défaut du volet contient un pointeur vers [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md) et redirige la plupart des opérations sur le groupe de volets \(tels que redimensionner un volet, ou ancrer un volet ou un conteneur différent\) au gestionnaire du conteneur.  Chaque volet d'ancrage met à jour un pointeur vers son séparateur par défaut de volet.  
  
-   Un diviseur normal de volet divise seulement deux volets dans un conteneur.  Pour plus d'informations, consultez [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md).  
  
## Exemple  
 L'exemple suivant montre comment obtenir un objet d' `CPaneDivider` d'un objet d' `CWorkspaceBar` .  Cet extrait de code fait partie d' [Exemple de démonstration d'onglets MDI](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/CPP/cpanedivider-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## Configuration requise  
 **en\-tête :** afxPaneDivider.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager Class](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer Class](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager Class](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)