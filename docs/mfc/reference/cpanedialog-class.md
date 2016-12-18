---
title: "CPaneDialog Class | Microsoft Docs"
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
  - "CPaneDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPaneDialog class"
  - "CPaneDialog constructor"
  - "CPaneDialog::CreateObject method"
  - "CPaneDialog::OnEraseBkgnd method"
  - "CPaneDialog::OnLButtonDblClk method"
  - "CPaneDialog::OnLButtonDown method"
  - "CPaneDialog::OnUpdateCmdUI method"
  - "CPaneDialog::OnWindowPosChanging method"
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPaneDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CPaneDialog` prend en charge une boîte de dialogue non modale et ancrable.  
  
## Syntaxe  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CPaneDialog::CPaneDialog`|Constructeur par défaut.|  
|`CPaneDialog::~CPaneDialog`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPaneDialog::Create](../Topic/CPaneDialog::Create.md)|Crée une boîte de dialogue ancrable et la attaché à un objet d' `CPaneDialog` .|  
|`CPaneDialog::CreateObject`|Utilisé par l'infrastructure pour créer une instance dynamique de ce type de classe.|  
|`CPaneDialog::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|[CPaneDialog::HandleInitDialog](../Topic/CPaneDialog::HandleInitDialog.md)|Gère le message de [WM\_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) .  \(Redéfinit `CBasePane::HandleInitDialog`.\)|  
|`CPaneDialog::OnEraseBkgnd`|Gérer le message de [WM\_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) .  \(Redéfinit [CWnd::OnEraseBkgnd](../Topic/CWnd::OnEraseBkgnd.md).\)|  
|`CPaneDialog::OnLButtonDblClk`|Gérer le message de [WM\_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) .  \(Redéfinit [CWnd::OnLButtonDblClk](../Topic/CWnd::OnLButtonDblClk.md).\)|  
|`CPaneDialog::OnLButtonDown`|Gérer le message de [WM\_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) .  \(Redéfinit [CWnd::OnLButtonDown](../Topic/CWnd::OnLButtonDown.md).\)|  
|`CPaneDialog::OnUpdateCmdUI`|Appelé par l'infrastructure pour mettre à jour la fenêtre boîte de dialogue.  \(Substitutions [CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/fr-fr/5dd61606-1c12-40d4-b024-f3839aa5e2e0).\)|  
|`CPaneDialog::OnWindowPosChanging`|Gère le message de [WM\_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) .  \(Redéfinit [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md).\)|  
|[CPaneDialog::SetOccDialogInfo](../Topic/CPaneDialog::SetOccDialogInfo.md)|Spécifie le modèle pour une boîte de dialogue qui est un conteneur de contrôle OLE.|  
  
## Notes  
 Construisez un objet d' `CPaneDialog` en deux étapes.  D'abord, construisez l'objet dans votre code.  Ensuite, appelez [CPaneDialog::Create](../Topic/CPaneDialog::Create.md).  Vous devez spécifier un ID valide de nom du modèle ou de modèle de ressource et passer un pointeur vers la fenêtre parente.  Sinon, les échecs de processus de création.  La boîte de dialogue doit spécifier le style de WS\_CHILD et de WS\_VISIBLE.  Nous recommandons que vous spécifiez également les styles de WS\_CLIPCHILDREN et de WS\_CLIPSIBLINGS.  Pour plus d'informations, consultez [Styles de fenêtre](../../mfc/reference/window-styles.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## Configuration requise  
 **en\-tête :** afxpanedialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [Styles de fenêtre](../../mfc/reference/window-styles.md)