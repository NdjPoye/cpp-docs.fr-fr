---
title: "CMFCOutlookBarPane Class | Microsoft Docs"
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
  - "CMFCOutlookBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanBeRestored method"
  - "CMFCOutlookBarPane class"
  - "Dock method"
  - "IsChangeState method"
  - "OnBeforeFloat method"
  - "RestoreOriginalstate method"
  - "SmartUpdate method"
ms.assetid: 094e2ef3-a118-487e-a4cc-27626108fe08
caps.latest.revision: 30
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Un contrôle dérivé de [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) qui peut être inséré dans une barre Outlook \([CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)\).  Le volet de barre Outlook contient une colonne pour les boutons.  L'utilisateur peut défiler la liste et BAS de boutons si elle est supérieure au volet.  Lorsque l'utilisateur se détache un volet de barre Outlook de la barre Outlook, elle peut flottant ou l'ancrer dans la fenêtre frame principale.  
  
## Syntaxe  
  
```  
class CMFCOutlookBarPane : public CMFCToolBar  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCOutlookBarPane::CMFCOutlookBarPane`|Constructeur par défaut.|  
|`CMFCOutlookBarPane::~CMFCOutlookBarPane`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCOutlookBarPane::AddButton](../Topic/CMFCOutlookBarPane::AddButton.md)|Ajoute un bouton dans le volet de barre Outlook.|  
|[CMFCOutlookBarPane::CanBeAttached](../Topic/CMFCOutlookBarPane::CanBeAttached.md)|Détermine si le volet peut être ancré à un volet ou une fenêtre frame différent.  \(Substitutions [CBasePane::CanBeAttached](../Topic/CBasePane::CanBeAttached.md).\)|  
|`CMFCOutlookBarPane::CanBeRestored`|Détermine si le système peut restaurer une barre d'outils à son état d'origine après personnalisation.  \(Substitutions [CMFCToolBar::CanBeRestored](../Topic/CMFCToolBar::CanBeRestored.md).\)|  
|[CMFCOutlookBarPane::ClearAll](../Topic/CMFCOutlookBarPane::ClearAll.md)|Libère les ressources utilisées par les images dans le volet de barre Outlook.|  
|[CMFCOutlookBarPane::Create](../Topic/CMFCOutlookBarPane::Create.md)|Crée le volet de barre Outlook.|  
|`CMFCOutlookBarPane::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CMFCOutlookBarPane::Dock`|Appelé par l'infrastructure pour ancrer le volet de barre Outlook. \(Substitutions `CPane::Dock`.\)|  
|[CMFCOutlookBarPane::EnablePageScrollMode](../Topic/CMFCOutlookBarPane::EnablePageScrollMode.md)|Spécifie si les flèches de défilement dans le volet de barre Outlook avancent la liste des boutons par la page, ou par le bouton.|  
|[CMFCOutlookBarPane::GetRegularColor](../Topic/CMFCOutlookBarPane::GetRegularColor.md)|Retourne la couleur \(non sélectionnée\) normale de texte du volet de barre Outlook.|  
|`CMFCOutlookBarPane::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CMFCOutlookBarPane::IsBackgroundTexture](../Topic/CMFCOutlookBarPane::IsBackgroundTexture.md)|Détermine si une image d'arrière\-plan chargé pour le volet de barre Outlook.|  
|`CMFCOutlookBarPane::IsChangeState`|Détermine si un volet flottant peut être ancré.  \(Substitutions `CPane::IsChangeState`.\)|  
|[CMFCOutlookBarPane::IsDrawShadedHighlight](../Topic/CMFCOutlookBarPane::IsDrawShadedHighlight.md)|Détermine si la bordure du bouton est occultée lorsqu'un clic est mis en surbrillance et une image d'arrière\-plan s'affiche.|  
|`CMFCOutlookBarPane::OnBeforeFloat`|Appelé par l'infrastructure lorsqu'un volet est sur le point de flotter.  \(Substitutions [CPane::OnBeforeFloat](../Topic/CPane::OnBeforeFloat.md).\)|  
|[CMFCOutlookBarPane::RemoveButton](../Topic/CMFCOutlookBarPane::RemoveButton.md)|Supprime le bouton qui a un ID de commande spécifiée|  
|`CMFCOutlookBarPane::RestoreOriginalstate`|Restaure l'état d'origine d'une barre d'outils.  \(Substitutions [CMFCToolBar::RestoreOriginalState](../Topic/CMFCToolBar::RestoreOriginalState.md).\)|  
|[CMFCOutlookBarPane::SetBackColor](../Topic/CMFCOutlookBarPane::SetBackColor.md)|Définit la couleur d'arrière\-plan.|  
|[CMFCOutlookBarPane::SetBackImage](../Topic/CMFCOutlookBarPane::SetBackImage.md)|Définit l'image d'arrière\-plan.|  
|[CMFCOutlookBarPane::SetDefaultState](../Topic/CMFCOutlookBarPane::SetDefaultState.md)|Réinitialise le volet de barre Outlook à l'ensemble de boutons.|  
|[CMFCOutlookBarPane::SetExtraSpace](../Topic/CMFCOutlookBarPane::SetExtraSpace.md)|Définit le nombre de pixels de la marge intérieure utilisés autour de les boutons dans le volet de barre Outlook.|  
|[CMFCOutlookBarPane::SetTextColor](../Topic/CMFCOutlookBarPane::SetTextColor.md)|Définit les couleurs du arial regular et du texte sélectionné dans le volet de barre Outlook.|  
|[CMFCOutlookBarPane::SetTransparentColor](../Topic/CMFCOutlookBarPane::SetTransparentColor.md)|Définit la couleur transparente pour le volet de barre Outlook.|  
|`CMFCOutlookBarPane::SmartUpdate`|Utilisé en interne pour mettre à jour la barre Outlook.  \(Substitutions `CMFCToolBar::SmartUpdate`.\)|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCOutlookBarPane::EnableContextMenuItems](../Topic/CMFCOutlookBarPane::EnableContextMenuItems.md)|Spécifie que les éléments de menu contextuel s'affiche en mode de personnalisation.|  
|[CMFCOutlookBarPane::RemoveAllButtons](../Topic/CMFCOutlookBarPane::RemoveAllButtons.md)|Supprime tous les boutons du volet de barre Outlook.  \(Substitutions [CMFCToolBar::RemoveAllButtons](../Topic/CMFCToolBar::RemoveAllButtons.md).\)|  
  
## Notes  
 Pour plus d'informations sur la manière d'implémenter une barre Outlook, consultez [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Pour obtenir un exemple d'une barre Outlook, consultez l'exemple de projet OutlookDemo.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes de classe d' `CMFCOutlookBarPane` .  L'exemple montre comment créer un volet de barre Outlook, activer le mode de défilement de page, activer l'ancrage, et définir la couleur d'arrière\-plan de la barre Outlook.  Cet extrait de code fait partie de [Multi exemple de vues Outlook](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookMultiViews#3](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_1.h)]  
[!code-cpp[NVC_MFC_OutlookMultiViews#4](../../mfc/reference/codesnippet/CPP/cmfcoutlookbarpane-class_2.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCOutlookBarPane](../../mfc/reference/cmfcoutlookbarpane-class.md)  
  
## Configuration requise  
 **en\-tête :** afxoutlookbarpane.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCOutlookBar, Classe](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)