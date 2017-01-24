---
title: "Classe CBaseTabbedPane | Microsoft Docs"
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
  - "CBaseTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTabbedPane, classe"
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classe CBaseTabbedPane
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Étend les fonctionnalités de [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) pour prendre en charge la création de fenêtres avec tabulation.  
  
## Syntaxe  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)|Ajoute un nouvel onglet à un volet avec tabulation.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md)|Spécifie si un volet avec tabulation vide peut être perdues.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](../Topic/CBaseTabbedPane::ApplyRestoredTabInfo.md)|Applique les paramètres de tabulation, qui sont chargées du Registre, un volet avec tabulation.|  
|[CBaseTabbedPane::CanFloat](../Topic/CBaseTabbedPane::CanFloat.md)|Détermine si le volet flottant peut.  \(Substitutions [CBasePane::CanFloat](../Topic/CBasePane::CanFloat.md).\)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md)|Détermine si la légende pour le volet avec tabulation doit afficher le même texte de l'onglet actif.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](../Topic/CBaseTabbedPane::ConvertToTabbedDocument.md)|\(Substitutions [CDockablePane::ConvertToTabbedDocument](../Topic/CDockablePane::ConvertToTabbedDocument.md).\)|  
|[CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)|Convertit un ou plusieurs volets ancrables aux documents avec onglet MDI.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](../Topic/CBaseTabbedPane::EnableSetCaptionTextToTabName.md)|Active ou désactive la capacité du volet avec tabulation de synchroniser le texte de légende avec le texte de l'étiquette sur l'onglet actif.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](../Topic/CBaseTabbedPane::FillDefaultTabsOrderArray.md)|Restaure l'ordre de tabulation interne à un état par défaut.|  
|[CBaseTabbedPane::FindBarByTabNumber](../Topic/CBaseTabbedPane::FindBarByTabNumber.md)|Retourne un volet qui réside dans un onglet à l'onglet est identifié par un index de base zéro d'onglet.|  
|||  
|[CBaseTabbedPane::FindPaneByID](../Topic/CBaseTabbedPane::FindPaneByID.md)|Retourne un volet qui est identifié par l'ID de volet|  
|[CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)|Flotte un volet, mais uniquement si le volet se trouve actuellement dans une table détachable.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](../Topic/CBaseTabbedPane::GetDefaultTabsOrder.md)|Retourne la commande par défaut d'onglets dans le volet.|  
|[CBaseTabbedPane::GetFirstVisibleTab](../Topic/CBaseTabbedPane::GetFirstVisibleTab.md)|Extrait un pointeur vers la première table affiche.|  
|[CBaseTabbedPane::GetMinSize](../Topic/CBaseTabbedPane::GetMinSize.md)|Récupère le minimum autorisé la taille du volet.  \(Substitutions [CPane::GetMinSize](../Topic/CPane::GetMinSize.md).\)|  
|[CBaseTabbedPane::GetPaneIcon](../Topic/CBaseTabbedPane::GetPaneIcon.md)|Retourne un handle vers l'icône de volet.  \(Substitutions [CBasePane::GetPaneIcon](../Topic/CBasePane::GetPaneIcon.md).\)|  
|[CBaseTabbedPane::GetPaneList](../Topic/CBaseTabbedPane::GetPaneList.md)|Retourne une liste des volets qui sont contenus dans le volet avec tabulation.|  
|[CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md)|Retourne les rectangles englobants pour les zones d'onglet de haut et bas.|  
|[CBaseTabbedPane::GetTabsNum](../Topic/CBaseTabbedPane::GetTabsNum.md)|Retourne le nombre d'onglets dans une fenêtre d'onglet.|  
|[CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md)|Obtient la fenêtre \(encapsulée\) sous\-jacente à onglet.|  
|[CBaseTabbedPane::GetVisibleTabsNum](../Topic/CBaseTabbedPane::GetVisibleTabsNum.md)|Retourne le nombre d'onglets affichés.|  
|[CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)|Détermine si dans le volet avec tabulation peut être basculé masquer automatiquement le mode.|  
|[CBaseTabbedPane::IsHideSingleTab](../Topic/CBaseTabbedPane::IsHideSingleTab.md)|Détermine si le volet avec tabulation est masquée si un seul onglet s'affiche.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Utilisé en interne pendant la sérialisation.|  
|[CBaseTabbedPane::RecalcLayout](../Topic/CBaseTabbedPane::RecalcLayout.md)|Recalcule les informations de disposition pour le volet.  \(Substitutions [CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md).\)|  
|[CBaseTabbedPane::RemovePane](../Topic/CBaseTabbedPane::RemovePane.md)|Supprime un volet du volet avec tabulation.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Utilisé en interne pendant la sérialisation.|  
|`CBaseTabbedPane::Serialize`|\(Substitutions [CDockablePane::Serialize](http://msdn.microsoft.com/fr-fr/09787e59-e446-4e76-894b-206d303dcfd6).\)|  
|`CBaseTabbedPane::SerializeTabWindow`|Utilisé en interne pendant la sérialisation.|  
|[CBaseTabbedPane::SetAutoDestroy](../Topic/CBaseTabbedPane::SetAutoDestroy.md)|Détermine si la barre de contrôles avec tabulation est perdue automatiquement.|  
|[CBaseTabbedPane::SetAutoHideMode](../Topic/CBaseTabbedPane::SetAutoHideMode.md)|Bascule le volet d'ancrage entre l'affichage et masque automatiquement le mode.  \(Substitutions [CDockablePane::SetAutoHideMode](../Topic/CDockablePane::SetAutoHideMode.md).\)|  
|[CBaseTabbedPane::ShowTab](../Topic/CBaseTabbedPane::ShowTab.md)|Affiche ou masque une table.|  
  
## Notes  
 Cette classe est une classe abstraite et ne peut pas être instanciée.  Il implémente les services communs à tous les types de volets avec tabulation.  
  
 Actuellement, la bibliothèque inclut deux classes dérivées avec tabulation du volet : [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md) et [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Un objet d' `CBaseTabbedPane` encapsule un pointeur vers un objet de [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) .  [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) devient alors une fenêtre enfant du volet avec tabulation.  
  
 Pour plus d'informations sur la création de volets avec tabulation, consultez [CDockablePane Class](../../mfc/reference/cdockablepane-class.md), [CTabbedPane Class](../../mfc/reference/ctabbedpane-class.md), et le [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
## Configuration requise  
 **En\-tête :** afxBaseTabbedPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)