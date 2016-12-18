---
title: "IOleObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IOleObjectImpl"
  - "ATL.IOleObjectImpl<T>"
  - "ATL::IOleObjectImpl"
  - "ATL::IOleObjectImpl<T>"
  - "IOleObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), communication between container and control"
  - "IOleObject, ATL (implémentation)"
  - "IOleObjectImpl class"
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOleObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et est l'interface principale dans laquelle un conteneur communique avec un contrôle.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IOleObjectImpl :  
public IOleObject  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IOleObjectImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IOleObjectImpl::Advise](../Topic/IOleObjectImpl::Advise.md)|Établit une connexion consultative avec le contrôle.|  
|[IOleObjectImpl::Close](../Topic/IOleObjectImpl::Close.md)|Remplace l'état du contrôle en cours de exécution par chargé.|  
|[IOleObjectImpl::DoVerb](../Topic/IOleObjectImpl::DoVerb.md)|Indique le contrôle d'exécuter une de ses actions énumérées.|  
|[IOleObjectImpl::DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md)|Indique le contrôle ignore tout état canceled qu'il gère.|  
|[IOleObjectImpl::DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md)|Indique le contrôle de supprimer son interface utilisateur de la vue.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md)|Exécute le contrôle et installe la fenêtre, mais n'installe pas l'interface utilisateur du contrôle.|  
|[IOleObjectImpl::DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md)|Entraîne le contrôle ouvert\- d'être modifié dans une fenêtre séparée.|  
|[IOleObjectImpl::DoVerbPrimary](../Topic/IOleObjectImpl::DoVerbPrimary.md)|Exécute l'action spécifiée lorsque l'utilisateur double\-clique sur le contrôle.  Le contrôle définit l'action, d'activer généralement le contrôle sur place.|  
|[IOleObjectImpl::DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md)|Montre un contrôle récemment insérée à l'utilisateur.|  
|[IOleObjectImpl::DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md)|Lance le visuelle du contrôle et affiche l'interface utilisateur du contrôle, telles que les menus et les barres d'outils.|  
|[IOleObjectImpl::EnumAdvise](../Topic/IOleObjectImpl::EnumAdvise.md)|Énumère les connexions consultatives du contrôle.|  
|[IOleObjectImpl::EnumVerbs](../Topic/IOleObjectImpl::EnumVerbs.md)|Énumère les actions du contrôle.|  
|[IOleObjectImpl::GetClientSite](../Topic/IOleObjectImpl::GetClientSite.md)|Récupère le site cliente du contrôle.|  
|[IOleObjectImpl::GetClipboardData](../Topic/IOleObjectImpl::GetClipboardData.md)|Récupère les données du presse\-papiers.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetExtent](../Topic/IOleObjectImpl::GetExtent.md)|Extrait l'étendue de la zone d'affichage du contrôle.|  
|[IOleObjectImpl::GetMiscStatus](../Topic/IOleObjectImpl::GetMiscStatus.md)|Extrait l'état du contrôle.|  
|[IOleObjectImpl::GetMoniker](../Topic/IOleObjectImpl::GetMoniker.md)|Récupère le moniker du contrôle.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleObjectImpl::GetUserClassID](../Topic/IOleObjectImpl::GetUserClassID.md)|Récupère l'identificateur de classe du contrôle.|  
|[IOleObjectImpl::GetUserType](../Topic/IOleObjectImpl::GetUserType.md)|Extrait le nom d'utilisateur du contrôle.|  
|[IOleObjectImpl::InitFromData](../Topic/IOleObjectImpl::InitFromData.md)|Initialise le contrôle de données sélectionnées.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleObjectImpl::IsUpToDate](../Topic/IOleObjectImpl::IsUpToDate.md)|Contrôle si le contrôle est à jour.  L'implémentation ATL retourne `S_OK`.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](../Topic/IOleObjectImpl::OnPostVerbDiscardUndo.md)|Appelé par [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) après l'état d'annulation est ignoré.|  
|[IOleObjectImpl::OnPostVerbHide](../Topic/IOleObjectImpl::OnPostVerbHide.md)|Appelé par [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) après le contrôle est masqué.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPostVerbInPlaceActivate.md)|Appelé par [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) après le contrôle est activé en place.|  
|[IOleObjectImpl::OnPostVerbOpen](../Topic/IOleObjectImpl::OnPostVerbOpen.md)|Appelé par [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) après le contrôle a été ouvert pour la modifier dans une fenêtre séparée.|  
|[IOleObjectImpl::OnPostVerbShow](../Topic/IOleObjectImpl::OnPostVerbShow.md)|Appelé par [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) fois que le contrôle a été rendu visible.|  
|[IOleObjectImpl::OnPostVerbUIActivate](../Topic/IOleObjectImpl::OnPostVerbUIActivate.md)|Appelé par [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) une fois l'interface utilisateur du contrôle a été activée.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](../Topic/IOleObjectImpl::OnPreVerbDiscardUndo.md)|Appelé par [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) avant l'état d'annulation est ignoré.|  
|[IOleObjectImpl::OnPreVerbHide](../Topic/IOleObjectImpl::OnPreVerbHide.md)|Appelé par [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) avant que le contrôle est masqué.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPreVerbInPlaceActivate.md)|Appelé par [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) avant que le contrôle est activé en place.|  
|[IOleObjectImpl::OnPreVerbOpen](../Topic/IOleObjectImpl::OnPreVerbOpen.md)|Appelé par [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md) avant que le contrôle a été ouvert pour la modifier dans une fenêtre séparée.|  
|[IOleObjectImpl::OnPreVerbShow](../Topic/IOleObjectImpl::OnPreVerbShow.md)|Appelé par [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md) avant que le contrôle a été rendu visible.|  
|[IOleObjectImpl::OnPreVerbUIActivate](../Topic/IOleObjectImpl::OnPreVerbUIActivate.md)|Appelé par [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md) avant que l'interface utilisateur du contrôle a été activée.|  
|[IOleObjectImpl::SetClientSite](../Topic/IOleObjectImpl::SetClientSite.md)|Indique le contrôle autour de son site client dans le conteneur.|  
|[IOleObjectImpl::SetColorScheme](../Topic/IOleObjectImpl::SetColorScheme.md)|Recommandé un modèle de couleurs à l'application du contrôle éventuelle.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleObjectImpl::SetExtent](../Topic/IOleObjectImpl::SetExtent.md)|Définit l'étendue de la zone d'affichage du contrôle.|  
|[IOleObjectImpl::SetHostNames](../Topic/IOleObjectImpl::SetHostNames.md)|Indique au contrôle les noms de l'application conteneur et du document conteneur.|  
|[IOleObjectImpl::SetMoniker](../Topic/IOleObjectImpl::SetMoniker.md)|Indique au contrôle quel est son moniker.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IOleObjectImpl::Unadvise](../Topic/IOleObjectImpl::Unadvise.md)|Supprime une connexion consultative avec le contrôle.|  
|[IOleObjectImpl::Update](../Topic/IOleObjectImpl::Update.md)|Gère le contrôle.  L'implémentation ATL retourne `S_OK`.|  
  
## Notes  
 L'interface d' [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709) est l'interface principale dans laquelle un conteneur communique avec un contrôle.  La classe `IOleObjectImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)