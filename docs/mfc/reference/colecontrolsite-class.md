---
title: "COleControlSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlSite class"
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleControlSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les interfaces de contrôles côté client personnalisées.  
  
## Syntaxe  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlSite::COleControlSite](../Topic/COleControlSite::COleControlSite.md)|Construit un objet `COleControlSite`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlSite::BindDefaultProperty](../Topic/COleControlSite::BindDefaultProperty.md)|Lie la propriété par défaut du contrôle hébergé à une source de données.|  
|[COleControlSite::BindProperty](../Topic/COleControlSite::BindProperty.md)|Lie une propriété du contrôle hébergé à une source de données.|  
|[COleControlSite::CreateControl](../Topic/COleControlSite::CreateControl.md)|Crée un contrôle ActiveX hébergé.|  
|[COleControlSite::DestroyControl](../Topic/COleControlSite::DestroyControl.md)|Perd le contrôle hébergé.|  
|[COleControlSite::DoVerb](../Topic/COleControlSite::DoVerb.md)|Exécute un verbe spécifique du contrôle hébergé.|  
|[COleControlSite::EnableDSC](../Topic/COleControlSite::EnableDSC.md)|Permet d'approvisionnement de données pour un site de contrôle.|  
|[COleControlSite::EnableWindow](../Topic/COleControlSite::EnableWindow.md)|Active le site de contrôle.|  
|[COleControlSite::FreezeEvents](../Topic/COleControlSite::FreezeEvents.md)|Spécifie si le site de contrôle accepte des événements.|  
|[COleControlSite::GetDefBtnCode](../Topic/COleControlSite::GetDefBtnCode.md)|Récupère le code de bouton par défaut du contrôle hébergé.|  
|[COleControlSite::GetDlgCtrlID](../Topic/COleControlSite::GetDlgCtrlID.md)|Récupère l'identificateur du contrôle.|  
|[COleControlSite::GetEventIID](../Topic/COleControlSite::GetEventIID.md)|Récupère l'ID d'une interface d'événements pour un contrôle hébergé.|  
|[COleControlSite::GetExStyle](../Topic/COleControlSite::GetExStyle.md)|Récupère les styles étendus du site de contrôle.|  
|[COleControlSite::GetProperty](../Topic/COleControlSite::GetProperty.md)|Extrait une propriété spécifique du contrôle hébergé.|  
|[COleControlSite::GetStyle](../Topic/COleControlSite::GetStyle.md)|Récupère les styles du site de contrôle.|  
|[COleControlSite::GetWindowText](../Topic/COleControlSite::GetWindowText.md)|Extrait le texte du contrôle hébergé.|  
|[COleControlSite::InvokeHelper](../Topic/COleControlSite::InvokeHelper.md)|Appelez une méthode spécifique du contrôle hébergé.|  
|[COleControlSite::InvokeHelperV](../Topic/COleControlSite::InvokeHelperV.md)|Appelez une méthode spécifique du contrôle hébergé par une liste d'arguments variable.|  
|[COleControlSite::IsDefaultButton](../Topic/COleControlSite::IsDefaultButton.md)|Détermine si le contrôle est le bouton par défaut dans la fenêtre.|  
|[COleControlSite::IsWindowEnabled](../Topic/COleControlSite::IsWindowEnabled.md)|Contrôle l'état visible du site de contrôle.|  
|[COleControlSite::ModifyStyle](../Topic/COleControlSite::ModifyStyle.md)|Modifie les styles étendus actuels du site de contrôle.|  
|[COleControlSite::ModifyStyleEx](../Topic/COleControlSite::ModifyStyleEx.md)|Modifie les styles actuels du site de contrôle.|  
|[COleControlSite::MoveWindow](../Topic/COleControlSite::MoveWindow.md)|Modifie la position du site de contrôle.|  
|[COleControlSite::QuickActivate](../Topic/COleControlSite::QuickActivate.md)|Rapide lance le contrôle hébergé.|  
|[COleControlSite::SafeSetProperty](../Topic/COleControlSite::SafeSetProperty.md)|Définit une propriété ou une méthode du contrôle sans risque de lever une exception.|  
|[COleControlSite::SetDefaultButton](../Topic/COleControlSite::SetDefaultButton.md)|Définit le bouton par défaut dans la fenêtre.|  
|[COleControlSite::SetDlgCtrlID](../Topic/COleControlSite::SetDlgCtrlID.md)|Récupère l'identificateur du contrôle.|  
|[COleControlSite::SetFocus](../Topic/COleControlSite::SetFocus.md)|Définit le focus sur le site de contrôle.|  
|[COleControlSite::SetProperty](../Topic/COleControlSite::SetProperty.md)|Définit une propriété spécifique du contrôle hébergé.|  
|[COleControlSite::SetPropertyV](../Topic/COleControlSite::SetPropertyV.md)|Définit une propriété spécifique du contrôle hébergé par une liste d'arguments variable.|  
|[COleControlSite::SetWindowPos](../Topic/COleControlSite::SetWindowPos.md)|Définit la position du site de contrôle.|  
|[COleControlSite::SetWindowText](../Topic/COleControlSite::SetWindowText.md)|Définit le texte du contrôle hébergé.|  
|[COleControlSite::ShowWindow](../Topic/COleControlSite::ShowWindow.md)|Affiche ou masque le site de contrôle.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlSite::GetControlInfo](../Topic/COleControlSite::GetControlInfo.md)|Récupère les informations et les mnémoniques de clavier pour le contrôle hébergé.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControlSite::m\_bIsWindowless](../Topic/COleControlSite::m_bIsWindowless.md)|Détermine si le contrôle hébergé est un contrôle sans fenêtre.|  
|[COleControlSite::m\_ctlInfo](../Topic/COleControlSite::m_ctlInfo.md)|Contient des informations sur la gestion du clavier pour le contrôle.|  
|[COleControlSite::m\_dwEventSink](../Topic/COleControlSite::m_dwEventSink.md)|Le cookie du point de connexion du contrôle.|  
|[COleControlSite::m\_dwMiscStatus](../Topic/COleControlSite::m_dwMiscStatus.md)|Les divers états du contrôle hébergé.|  
|[COleControlSite::m\_dwPropNotifySink](../Topic/COleControlSite::m_dwPropNotifySink.md)|Le cookie d' `IPropertyNotifySink` du contrôle.|  
|[COleControlSite::m\_dwStyle](../Topic/COleControlSite::m_dwStyle.md)|Les styles du contrôle hébergé.|  
|[COleControlSite::m\_hWnd](../Topic/COleControlSite::m_hWnd.md)|Le handle du site de contrôle.|  
|[COleControlSite::m\_iidEvents](../Topic/COleControlSite::m_iidEvents.md)|L'ID de l'interface d'événements pour le contrôle hébergé.|  
|[COleControlSite::m\_nID](../Topic/COleControlSite::m_nID.md)|L'ID du contrôle hébergé.|  
|[COleControlSite::m\_pActiveObject](../Topic/COleControlSite::m_pActiveObject.md)|Pointeur vers l'objet d' `IOleInPlaceActiveObject` du contrôle hébergé.|  
|[COleControlSite::m\_pCtrlCont](../Topic/COleControlSite::m_pCtrlCont.md)|Le conteneur du contrôle hébergé.|  
|[COleControlSite::m\_pInPlaceObject](../Topic/COleControlSite::m_pInPlaceObject.md)|Pointeur vers l'objet d' `IOleInPlaceObject` du contrôle hébergé.|  
|[COleControlSite::m\_pObject](../Topic/COleControlSite::m_pObject.md)|Pointeur vers l'interface d' `IOleObjectInterface` du contrôle.|  
|[COleControlSite::m\_pWindowlessObject](../Topic/COleControlSite::m_pWindowlessObject.md)|Pointeur vers l'interface d' `IOleInPlaceObjectWindowless` du contrôle.|  
|[COleControlSite::m\_pWndCtrl](../Topic/COleControlSite::m_pWndCtrl.md)|Pointeur vers l'objet window pour le contrôle hébergé.|  
|[COleControlSite::m\_rect](../Topic/COleControlSite::m_rect.md)|Les dimensions du site de contrôle.|  
  
## Notes  
 Cette prise en charge est la première méthode par laquelle un contrôle ActiveX incorporé obtient des informations sur l'emplacement et l'étendue de son site d'affichage, de son moniker, de son interface utilisateur, de ses propriétés ambiantes, et d'autres ressources fournies par son conteneur.  `COleControlSite` implémente entièrement [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638), **IBoundObjectSite**, **INotifyDBEvents**, interfaces d' [IRowSetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) .  En outre, l'interface IDispatch \(fournissant la prise en charge pour les propriétés ambiantes et les récepteurs d'événements\) est également implémentée.  
  
 Pour créer un site de contrôle ActiveX à l'aide de `COleControlSite`, dérivez une classe d' `COleControlSite`.  Dans votre `CWnd`classe dérivée pour la substitution de conteneur \(par exemple, votre boîte de dialogue\) la fonction de **CWnd::CreateControlSite** .  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## Configuration requise  
 **Header:** afxocc.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleControlContainer Class](../../mfc/reference/colecontrolcontainer-class.md)