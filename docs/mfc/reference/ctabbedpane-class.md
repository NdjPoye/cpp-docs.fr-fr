---
title: "CTabbedPane Class | Microsoft Docs"
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
  - "CTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabbedPane class"
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTabbedPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les fonctionnalités d'un volet à onglets détachables.  
  
## Syntaxe  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CTabbedPane::CTabbedPane`|Constructeur par défaut.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabbedPane::DetachPane](../Topic/CTabbedPane::DetachPane.md)|\(Substitue [CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md).\)|  
|[CTabbedPane::EnableTabAutoColor](../Topic/CTabbedPane::EnableTabAutoColor.md)|Active ou désactive la coloration automatique des onglets.|  
|[CTabbedPane::FloatTab](../Topic/CTabbedPane::FloatTab.md)|Fait flotter un volet, mais seulement si le volet réside actuellement dans un onglet détachable.  \(Substitue [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CTabbedPane::GetTabArea](../Topic/CTabbedPane::GetTabArea.md)|Retourne la taille et la position de la zone d'onglet dans la fenêtre à onglets.|  
|[CTabbedPane::GetTabWnd](../Topic/CTabbedPane::GetTabWnd.md)||  
|[CTabbedPane::HasAutoHideMode](../Topic/CTabbedPane::HasAutoHideMode.md)|Détermine si le volet à onglets peut passer en mode masquage automatique.  \(Substitue [CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md).\)|  
|[CTabbedPane::IsTabLocationBottom](../Topic/CTabbedPane::IsTabLocationBottom.md)|Détermine si les onglets sont situés au bas de la fenêtre.|  
|[CTabbedPane::ResetTabs](../Topic/CTabbedPane::ResetTabs.md)|Rétablit l'état par défaut de tous les volets à onglets.|  
|[CTabbedPane::SetTabAutoColors](../Topic/CTabbedPane::SetTabAutoColors.md)|Définit une liste de couleurs personnalisées qui peuvent être utilisées quand la fonctionnalité de couleur automatique est activée.|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CTabbedPane::m\_bTabsAlwaysTop](../Topic/CTabbedPane::m_bTabsAlwaysTop.md)|Emplacement par défaut des onglets dans l'application.|  
|[CTabbedPane::m\_pTabWndRTC](../Topic/CTabbedPane::m_pTabWndRTC.md)|Informations de classe runtime pour un objet dérivé de `CMFCTabCtrl` personnalisé.|  
  
## Notes  
 L'infrastructure crée automatiquement une instance de cette classe quand un utilisateur attache un volet à un autre en pointant vers la légende du deuxième volet.  Tous les volets à onglets créés par l'infrastructure ont un ID égal à \-1.  
  
 Pour spécifier des onglets normaux à la place d'onglets de style Outlook, passez le style `AFX_CBRS_REGULAR_TABS` à la méthode [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md).  
  
 Si vous créez un volet à onglets avec des onglets détachables, le volet risque d'être détruit automatiquement par l'infrastructure. Il est donc déconseillé de stocker le pointeur.  Pour obtenir un pointeur vers le volet à onglets, appelez la méthode `CBasePane::GetParentTabbedPane`.  
  
## Exemple  
 Dans cet exemple, nous créons un objet `CTabbedPane`.  Ensuite, nous utilisons [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md) pour attacher des onglets supplémentaires.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);  
if (!pTabbededBar->Create (_T(""), this, CRect (0, 0, 200, 200),  
                           TRUE,   
                           (UINT) -1,  
                           WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
                           WS_CLIPCHILDREN | CBRS_LEFT |    
                           CBRS_FLOAT_MULTI))  
{  
    TRACE0("Failed to create Solution Explorer bar\n");  
    return FALSE;      // fail to create  
}  
  
pTabbededBar->AddTab (&m_wndClassView);  
pTabbededBar->AddTab (&m_wndResourceView);  
pTabbededBar->AddTab (&m_wndFileView);  
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);  
DockPane(pTabbededBar);  
```  
  
## Exemple  
 Une autre façon de créer un objet de barre de contrôle à onglets est d'utiliser [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md).  La méthode `AttachToTabWnd` crée de façon dynamique un objet de volet à onglets à partir des informations de classe runtime définies par [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md).  
  
 Dans cet exemple, nous créons un volet à onglets de façon dynamique, joignons les deux onglets et rendons le deuxième onglet non détachable.  
  
```  
DockPane(&m_wndClassView);  
CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView, DM_SHOW, TRUE,  
                                  (CDockablePane**) &pTabbedBar);  
m_wndFileView.AttachToTabWnd (pTabbedBar, DM_SHOW, TRUE,  
                              (CDockablePane**) &pTabbedBar);  
pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1, FALSE);  
```  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## Configuration requise  
 **En\-tête :** afxTabbedPane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [Classe CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)