---
title: "CMFCOutlookBar, Classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCOutlookBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBar, classe"
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCOutlookBar, Classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un volet avec tabulation avec l'apparence visuelle **Volet de navigation** dans Microsoft Outlook 2000 et Outlook 2003.  L'objet d' `CMFCOutlookBar` contient un objet de [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md) et séries d'onglets.  Les tabulations peuvent être des objets de [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) ou `CWnd`\- objets dérivés.  À l'utilisateur, la barre Outlook apparaît comme un ensemble de boutons et d'une zone d'affichage.  Lorsque l'utilisateur clique sur un bouton, le volet de contrôle correspondant ou du bouton est affiché.  
  
## Syntaxe  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCOutlookBar::CMFCOutlookBar`|Constructeur par défaut.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|Destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](../Topic/CMFCOutlookBar::AllowDestroyEmptyTabbedPane.md)|Spécifie si un volet avec tabulation vide peut être perdues.  \(Substitutions [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md).\)|  
|[CMFCOutlookBar::CanAcceptPane](../Topic/CMFCOutlookBar::CanAcceptPane.md)|Détermine si un autre volet peut être ancré au volet de barre Outlook.  \(Substitutions CDockablePane::CanAcceptPane.\)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](../Topic/CMFCOutlookBar::CanSetCaptionTextToTabName.md)|Détermine si la légende pour le volet avec tabulation affiche le même texte de l'onglet actif.  \(Substitutions [CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md).\)|  
|[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)|Crée le contrôle de barre Outlook.|  
|[CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md)|Crée une barre personnalisée tableau Outlook.|  
|`CMFCOutlookBar::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](../Topic/CMFCOutlookBar::DoesAllowDynInsertBefore.md)|Détermine si un utilisateur peut ancrer une barre de contrôles au bord externe de la barre Outlook.|  
|[CMFCOutlookBar::FloatTab](../Topic/CMFCOutlookBar::FloatTab.md)|Flotte un volet, mais uniquement si le volet se trouve actuellement dans une table détachable.  \(Substitutions [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CMFCOutlookBar::GetButtonsFont](../Topic/CMFCOutlookBar::GetButtonsFont.md)|Retourne la police du texte sur les boutons de la barre Outlook.|  
|[CMFCOutlookBar::GetTabArea](../Topic/CMFCOutlookBar::GetTabArea.md)|Retourne la taille et la position des zones d'onglet sur la barre Outlook.  \(Substitutions [CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md).\)|  
|`CMFCOutlookBar::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet d' [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCOutlookBar::IsMode2003](../Topic/CMFCOutlookBar::IsMode2003.md)|Détermine si le comportement des imitateurs de barre Outlook qui Microsoft Office Outlook 2003 \(consultez les notes\).|  
|[CMFCOutlookBar::OnAfterAnimation](../Topic/CMFCOutlookBar::OnAfterAnimation.md)|Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) après l'onglet actif a été défini à l'aide de l'animation.|  
|[CMFCOutlookBar::OnBeforeAnimation](../Topic/CMFCOutlookBar::OnBeforeAnimation.md)|Appelé par [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) avant une page d'onglets est défini comme onglet actif à l'aide de l'animation.|  
|[CMFCOutlookBar::OnScroll](../Topic/CMFCOutlookBar::OnScroll.md)|Appelé par l'infrastructure si la barre Outlook fait défiler vers le haut ou vers le bas.|  
|[CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md)|Supprime une barre personnalisée tableau Outlook.|  
|[CMFCOutlookBar::SetButtonsFont](../Topic/CMFCOutlookBar::SetButtonsFont.md)|Définit la police du texte sur les boutons de la barre Outlook.|  
|[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md)|Spécifie si le comportement des imitateurs de barre Outlook qui Outlook 2003 \(consultez les notes\).|  
  
## Notes  
 Pour obtenir un exemple d'une barre Outlook, consultez [Exemple OutlookDemo : Application MFC OutlookDemo](../../top/visual-cpp-samples.md).  
  
## Implémenter la barre Outlook  
 Pour utiliser le contrôle d' `CMFCOutlookBar` dans votre application, suivez ces étapes :  
  
1.  Incluez un objet d' `CMFCOutlookBar` dans la classe de fenêtre frame principale.  
  
    ```  
    class CMainFrame : public CMDIFrameWnd  
     { ...  
         CMFCOutlookBar         m_wndOutlookBar;  
         CMFCOutlookBarPane     m_wndOutlookPane;  
    ... };  
    ```  
  
2.  Lors de le traitement du message d' `WM_CREATE` dans le frame principal, appelez la méthode de [CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md) pour créer le contrôle onglet de barre Outlook.  
  
    ```  
    m_wndOutlookBar.Create (_T("Shortcuts"), this, CRect (0, 0, 100, 100), ID_VIEW_OUTLOOKBAR, WS_CHILD | WS_VISIBLE | CBRS_LEFT);  
    ```  
  
3.  Obtient un pointeur vers `CMFCOutlookBarTabCtrl` sous\-jacent à l'aide de [CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md).  
  
    ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();  
    ```  
  
4.  Créez un objet de [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) pour chaque onglet qui contient des boutons.  
  
    ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar, AFX_DEFAULT_TOOLBAR_STYLE, ID_OUTLOOK_PANE_GENERAL, AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  
    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);  
    // add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About", ID_APP_ABOUT);  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open", ID_FILE_OPEN);  
    ```  
  
5.  Appelez [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) pour ajouter chaque nouvelle table.  Affectez au paramètre d' `bDetachable` à `FALSE` pour rendre une page non détachable.  Ou, utilisez [CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md) d'ajouter des pages détachables.  
  
    ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);   
    ```  
  
6.  Pour ajouter `CWnd`\- le contrôle dérivé \(par exemple, [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)\) comme onglet, créez le contrôle et l'appel [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) pour l'ajouter à la barre Outlook.  
  
> [!NOTE]
>  Vous devez utiliser des identificateurs uniques de contrôle pour chaque objet de [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) et pour chaque `CWnd`objet dérivé.  
  
 Pour ajouter dynamiquement ou supprimer des nouvelles pages au moment de l'exécution, utilisez [CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md) et [CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md).  
  
## Mode Outlook 2003  
 En mode Outlook 2003, les boutons de l'onglet sont positionnés en bas du volet de barre Outlook.  Lorsqu'il n'y a pas suffisamment de place pour afficher des boutons, ils sont affichés comme icônes dans une zone comme une barre d'outils le long de le bas du volet.  
  
 Utilisation [CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md) d'activer le mode Outlook 2003.  Utilisez [CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md) pour définir la bitmap qui contient les icônes affichées en bas de la barre Outlook.  Les icônes dans la bitmap doivent être classées par index de tabulation.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## Configuration requise  
 **En\-tête :** afxoutlookbar.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Classe CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)