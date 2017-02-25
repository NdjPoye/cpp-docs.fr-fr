---
title: "CComControlBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComControlBase"
  - "ATL.CComControlBase"
  - "ATL::CComControlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComControlBase class"
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComControlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour créer et gérer des contrôles ATL.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class ATL_NO_VTABLE CComControlBase  
  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControlBase::AppearanceType](../Topic/CComControlBase::AppearanceType.md)|Substitution si votre propriété d'actions d' `m_nAppearance` n'est pas de type `short`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControlBase::CComControlBase](../Topic/CComControlBase::CComControlBase.md)|Constructeur.|  
|[CComControlBase::~CComControlBase](../Topic/CComControlBase::~CComControlBase.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControlBase::ControlQueryInterface](../Topic/CComControlBase::ControlQueryInterface.md)|Extrait un pointeur vers l'interface demandée.|  
|[CComControlBase::DoesVerbActivate](../Topic/CComControlBase::DoesVerbActivate.md)|Vérifie que le paramètre d' `iVerb` celle utilisée par `IOleObjectImpl::DoVerb` que soit active l'interface utilisateur du contrôle \(`iVerb` égale `OLEIVERB_UIACTIVATE`\), définit l'action effectuée lorsque l'utilisateur double\-clique sur le contrôle \(`iVerb` égale `OLEIVERB_PRIMARY`\), affiche le contrôle \(`iVerb` égale `OLEIVERB_SHOW`\), ou lance le contrôle \(`iVerb` égale **OLEIVERB\_INPLACEACTIVATE**\).|  
|[CComControlBase::DoesVerbUIActivate](../Topic/CComControlBase::DoesVerbUIActivate.md)|Contrôle que le paramètre d' `iVerb` utilisé par `IOleObjectImpl::DoVerb` fait activer l'interface utilisateur du contrôle et retourne **TRUE**.|  
|[CComControlBase::DoVerbProperties](../Topic/CComControlBase::DoVerbProperties.md)|Affiche les pages de propriétés du contrôle.|  
|[CComControlBase::FireViewChange](../Topic/CComControlBase::FireViewChange.md)|Appelez cette méthode pour demander au conteneur de redessiner le contrôle, ou notifier les récepteurs de notifications stockés que la vue du contrôle a changé.|  
|[CComControlBase::GetAmbientAppearance](../Topic/CComControlBase::GetAmbientAppearance.md)|Récupère **DISPID\_AMBIENT\_APPEARANCE**, la configuration actuelle d'apparence pour le contrôle : 0 pour l'plate et 1 pour 3D.|  
|[CComControlBase::GetAmbientAutoClip](../Topic/CComControlBase::GetAmbientAutoClip.md)|Récupère **DISPID\_AMBIENT\_AUTOCLIP**, une balise qui indique si le conteneur prend en charge le découpage automatique de la zone affichage.|  
|[CComControlBase::GetAmbientBackColor](../Topic/CComControlBase::GetAmbientBackColor.md)|Récupère **DISPID\_AMBIENT\_BACKCOLOR**, la couleur d'arrière\-plan ambiante pour tous les contrôles, définie par le conteneur.|  
|[CComControlBase::GetAmbientCharSet](../Topic/CComControlBase::GetAmbientCharSet.md)|Récupère **DISPID\_AMBIENT\_CHARSET**, le jeu de caractères ambiant pour tous les contrôles, défini par le conteneur.|  
|[CComControlBase::GetAmbientCodePage](../Topic/CComControlBase::GetAmbientCodePage.md)|Récupère **DISPID\_AMBIENT\_CODEPAGE**, le jeu de caractères ambiant pour tous les contrôles, défini par le conteneur.|  
|[CComControlBase::GetAmbientDisplayAsDefault](../Topic/CComControlBase::GetAmbientDisplayAsDefault.md)|Récupère **DISPID\_AMBIENT\_DISPLAYASDEFAULT**, une balise qui est **TRUE** si le conteneur a marqué le contrôle dans ce site pour être un bouton par défaut, et par conséquent un contrôle bouton doit se dessiner avec un frame est épais.|  
|[CComControlBase::GetAmbientDisplayName](../Topic/CComControlBase::GetAmbientDisplayName.md)|Récupère **DISPID\_AMBIENT\_DISPLAYNAME**, le nom que le conteneur a fourni au contrôle.|  
|[CComControlBase::GetAmbientFont](../Topic/CComControlBase::GetAmbientFont.md)|Extrait un pointeur vers l'interface ambiante d' `IFont` du conteneur.|  
|[CComControlBase::GetAmbientFontDisp](../Topic/CComControlBase::GetAmbientFontDisp.md)|Extrait un pointeur vers l'interface de dispatch ambiante d' **IFontDisp** du conteneur.|  
|[CComControlBase::GetAmbientForeColor](../Topic/CComControlBase::GetAmbientForeColor.md)|Récupère **DISPID\_AMBIENT\_FORECOLOR**, la couleur de premier plan ambiante pour tous les contrôles, définie par le conteneur.|  
|[CComControlBase::GetAmbientLocaleID](../Topic/CComControlBase::GetAmbientLocaleID.md)|Récupère **DISPID\_AMBIENT\_LOCALEID**, l'identificateur du langage utilisé par le conteneur.|  
|[CComControlBase::GetAmbientMessageReflect](../Topic/CComControlBase::GetAmbientMessageReflect.md)|Récupère **DISPID\_AMBIENT\_MESSAGEREFLECT**, une balise qui indique si le conteneur souhaite recevoir des messages de fenêtre \(par exemple `WM_DRAWITEM`\) en tant qu'événements.|  
|[CComControlBase::GetAmbientPalette](../Topic/CComControlBase::GetAmbientPalette.md)|Récupère **DISPID\_AMBIENT\_PALETTE**, utilisé pour accéder à `HPALETTE`du conteneur.|  
|[CComControlBase::GetAmbientProperty](../Topic/CComControlBase::GetAmbientProperty.md)|Récupère la propriété du conteneur spécifiée par `id`.|  
|[CComControlBase::GetAmbientRightToLeft](../Topic/CComControlBase::GetAmbientRightToLeft.md)|Récupère **DISPID\_AMBIENT\_RIGHTTOLEFT**, la direction dans laquelle le contenu est affichée par le conteneur.|  
|[CComControlBase::GetAmbientScaleUnits](../Topic/CComControlBase::GetAmbientScaleUnits.md)|Récupère **DISPID\_AMBIENT\_SCALEUNITS**, les unités ambiantes du conteneur \(telles que pouces ou des centimètres\) pour les affichages de étiquetage.|  
|[CComControlBase::GetAmbientShowGrabHandles](../Topic/CComControlBase::GetAmbientShowGrabHandles.md)|Récupère **DISPID\_AMBIENT\_SHOWGRABHANDLES**, une balise qui indique si le conteneur permet le contrôle aux handles de manipulation d'affichage pour lui\-même si actif.|  
|[CComControlBase::GetAmbientShowHatching](../Topic/CComControlBase::GetAmbientShowHatching.md)|Récupère **DISPID\_AMBIENT\_SHOWHATCHING**, une balise qui indique si le conteneur permet au contrôle à afficher avec un modèle haché lorsque l'interface utilisateur est actif.|  
|[CComControlBase::GetAmbientSupportsMnemonics](../Topic/CComControlBase::GetAmbientSupportsMnemonics.md)|Récupère **DISPID\_AMBIENT\_SUPPORTSMNEMONICS**, une balise qui indique si le conteneur prend en charge les mnémoniques de clavier.|  
|[CComControlBase::GetAmbientTextAlign](../Topic/CComControlBase::GetAmbientTextAlign.md)|Récupère **DISPID\_AMBIENT\_TEXTALIGN**, l'alignement de texte préféré par le conteneur : 0 pour l'inscription standard \(les numéros redressent, texte gauche\), 1 pour l'alignement gauche, 2 pour l'alignement central, et 3 pour le bon alignement.|  
|[CComControlBase::GetAmbientTopToBottom](../Topic/CComControlBase::GetAmbientTopToBottom.md)|Récupère **DISPID\_AMBIENT\_TOPTOBOTTOM**, la direction dans laquelle le contenu est affichée par le conteneur.|  
|[CComControlBase::GetAmbientUIDead](../Topic/CComControlBase::GetAmbientUIDead.md)|Récupère **DISPID\_AMBIENT\_UIDEAD**, une balise qui indique si le conteneur souhaite le contrôle pour répondre aux actions d'interface utilisateur.|  
|[CComControlBase::GetAmbientUserMode](../Topic/CComControlBase::GetAmbientUserMode.md)|Récupère **DISPID\_AMBIENT\_USERMODE**, une balise qui indique si le conteneur est en mode exécution \(**TRUE**\) ou le mode Design \(**FALSE**\).|  
|[CComControlBase::GetDirty](../Topic/CComControlBase::GetDirty.md)|Retourne la valeur des données membre `m_bRequiresSave`.|  
|[CComControlBase::GetZoomInfo](../Topic/CComControlBase::GetZoomInfo.md)|Récupère les valeurs de x et y du numérateur et le dénominateur du facteur de zoom pour un contrôle activé pour la modification sur place.|  
|[CComControlBase::InPlaceActivate](../Topic/CComControlBase::InPlaceActivate.md)|Provoque le contrôle à la transition de l'état inactif valeur qui est ce que l'état du verbe dans `iVerb` indique.|  
|[CComControlBase::InternalGetSite](../Topic/CComControlBase::InternalGetSite.md)|Appelez cette méthode pour interroger le site de contrôle pour un pointeur vers l'interface reconnue.|  
|[CComControlBase::OnDraw](../Topic/CComControlBase::OnDraw.md)|Substituez cette méthode pour dessiner votre contrôle.|  
|[CComControlBase::OnDrawAdvanced](../Topic/CComControlBase::OnDrawAdvanced.md)|**OnDrawAdvanced** par défaut prépare un contexte normal de l'appareil pour dessiner, puis appelle la méthode du contrôle d' `OnDraw` de votre classe.|  
|[CComControlBase::OnKillFocus](../Topic/CComControlBase::OnKillFocus.md)|Contrôle auquel le contrôle est actif sur place et un site de contrôle valide, puis informe le conteneur que le contrôle a perdu le focus.|  
|[CComControlBase::OnMouseActivate](../Topic/CComControlBase::OnMouseActivate.md)|Contrôle que l'interface utilisateur est en mode utilisateur, puis démarre le contrôle.|  
|[CComControlBase::OnPaint](../Topic/CComControlBase::OnPaint.md)|Prépare le conteneur pour peindre, obtient la zone cliente du contrôle, puis appelle la méthode du contrôle d' `OnDraw` de la classe.|  
|[CComControlBase::OnSetFocus](../Topic/CComControlBase::OnSetFocus.md)|Contrôle auquel le contrôle est actif sur place et un site de contrôle valide, puis informe le conteneur que le contrôle a gagné le focus.|  
|[CComControlBase::PreTranslateAccelerator](../Topic/CComControlBase::PreTranslateAccelerator.md)|Substituez cette méthode pour fournir vos propres gestionnaires d'accélérateurs clavier.|  
|[CComControlBase::SendOnClose](../Topic/CComControlBase::SendOnClose.md)|Signale tous les récepteurs de notifications enregistrés avec le conteneur d'avertir que le contrôle a été fermé.|  
|[CComControlBase::SendOnDataChange](../Topic/CComControlBase::SendOnDataChange.md)|Signale tous les récepteurs de notifications enregistrés avec le conteneur d'informer que les paramètres ont été modifiés.|  
|[CComControlBase::SendOnRename](../Topic/CComControlBase::SendOnRename.md)|Signale tous les récepteurs de notifications enregistrés avec le conteneur d'avertir que le contrôle a un nouveau moniker.|  
|[CComControlBase::SendOnSave](../Topic/CComControlBase::SendOnSave.md)|Signale tous les récepteurs de notifications enregistrés avec le conteneur d'avertir que le contrôle a été enregistré.|  
|[CComControlBase::SendOnViewChange](../Topic/CComControlBase::SendOnViewChange.md)|Signale tous les récepteurs de notifications stockés que la vue du contrôle a changé.|  
|[CComControlBase::SetControlFocus](../Topic/CComControlBase::SetControlFocus.md)|Définit ou supprime le focus clavier vers ou du contrôle.|  
|[CComControlBase::SetDirty](../Topic/CComControlBase::SetDirty.md)|Définit le membre `m_bRequiresSave` à la valeur dans `bDirty`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComControlBase::m\_bAutoSize](../Topic/CComControlBase::m_bAutoSize.md)|La balise indiquant le contrôle ne peut pas être aucune autre taille.|  
|[CComControlBase::m\_bDrawFromNatural](../Topic/CComControlBase::m_bDrawFromNatural.md)|Marquez d'un indicateur indiquer cet `IDataObjectImpl::GetData` et `CComControlBase::GetZoomInfo` doit définir la taille de contrôle d' `m_sizeNatural` plutôt que d' `m_sizeExtent`.|  
|[CComControlBase::m\_bDrawGetDataInHimetric](../Topic/CComControlBase::m_bDrawGetDataInHimetric.md)|Marquez d'un indicateur indiquer cet `IDataObjectImpl::GetData` doit utiliser des unités HIMETRIC et non des pixels en dessinant.|  
|[CComControlBase::m\_bInPlaceActive](../Topic/CComControlBase::m_bInPlaceActive.md)|La balise indiquant le contrôle est actif sur place.|  
|[CComControlBase::m\_bInPlaceSiteEx](../Topic/CComControlBase::m_bInPlaceSiteEx.md)|La balise indiquant le conteneur en charge les fonctionnalités d'interface et de contrôle OCX96 d' **IOleInPlaceSiteEx** , telles que des contrôles sans fenêtre et sans scintillement.|  
|[CComControlBase::m\_bNegotiatedWnd](../Topic/CComControlBase::m_bNegotiatedWnd.md)|Marquez d'un indicateur indiquer si le contrôle a été en pourparlers avec le conteneur à propos de la prise en charge des fonctionnalités du contrôle OCX96 \(telles que des contrôles sans scintillement et sans fenêtre\), et si le contrôle est avec fenêtres ou sans fenêtre.|  
|[CComControlBase::m\_bRecomposeOnResize](../Topic/CComControlBase::m_bRecomposeOnResize.md)|La balise indiquant le contrôle souhaite recomposer la présentation lorsque le conteneur change la taille d'affichage du contrôle.|  
|[CComControlBase::m\_bRequiresSave](../Topic/CComControlBase::m_bRequiresSave.md)|La balise indiquant le contrôle a été modifié depuis qu'elle a été en dernier enregistrée.|  
|[CComControlBase::m\_bResizeNatural](../Topic/CComControlBase::m_bResizeNatural.md)|La balise indiquant le contrôle souhaite redimensionner son étendue naturelle \(sa taille physique unscaled\) lorsque le conteneur change la taille d'affichage du contrôle.|  
|[CComControlBase::m\_bUIActive](../Topic/CComControlBase::m_bUIActive.md)|Marquez d'un indicateur indiquer l'interface utilisateur du contrôle, telles que les menus et les barres d'outils, est actif.|  
|[CComControlBase::m\_bUsingWindowRgn](../Topic/CComControlBase::m_bUsingWindowRgn.md)|La balise indiquant le contrôle utilise la zone de fenêtre fourni aux conteneurs.|  
|[CComControlBase::m\_bWasOnceWindowless](../Topic/CComControlBase::m_bWasOnceWindowless.md)|La balise indiquant le contrôle a été sans fenêtre, mais peut ou ne peut pas être sans fenêtre maintenant.|  
|[CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md)|La balise indiquant le contrôle doit être fenêtrée, même si le conteneur en charge des contrôles sans fenêtre.|  
|[CComControlBase::m\_bWndLess](../Topic/CComControlBase::m_bWndLess.md)|La balise indiquant le contrôle est sans fenêtre.|  
|[CComControlBase::m\_hWndCD](../Topic/CComControlBase::m_hWndCD.md)|Contient une référence vers le handle de fenêtre associée au contrôle.|  
|[CComControlBase::m\_nFreezeEvents](../Topic/CComControlBase::m_nFreezeEvents.md)|Le nombre de fois le conteneur est figé des événements \(refusé pour recevoir des événements\) sans dégel intervenant des événements \(acceptation des événements\).|  
|[CComControlBase::m\_rcPos](../Topic/CComControlBase::m_rcPos.md)|La position en pixels du contrôle, exprimés en coordonnées du conteneur.|  
|[CComControlBase::m\_sizeExtent](../Topic/CComControlBase::m_sizeExtent.md)|L'étendue du contrôle en unités HIMETRIC \(chaque unité est de 0,01 millimètres\) pour un affichage particulier.|  
|[CComControlBase::m\_sizeNatural](../Topic/CComControlBase::m_sizeNatural.md)|La taille physique du contrôle en unités HIMETRIC \(chaque unité est de 0,01 millimètres\).|  
|[CComControlBase::m\_spAdviseSink](../Topic/CComControlBase::m_spAdviseSink.md)|Un pointeur direct à la connexion consultative sur le conteneur \( [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)du conteneur\).|  
|[CComControlBase::m\_spAmbientDispatch](../Topic/CComControlBase::m_spAmbientDispatch.md)|Un objet d' `CComDispatchDriver` qui vous permet de récupérer et définir les propriétés du conteneur via un pointeur d' `IDispatch` .|  
|[CComControlBase::m\_spClientSite](../Topic/CComControlBase::m_spClientSite.md)|Pointeur vers le site cliente du contrôle dans le conteneur.|  
|[CComControlBase::m\_spDataAdviseHolder](../Topic/CComControlBase::m_spDataAdviseHolder.md)|Fournit un moyen d'une norme de stocker les connexions consultatives entre les objets de données et les récepteurs de notifications.|  
|[CComControlBase::m\_spInPlaceSite](../Topic/CComControlBase::m_spInPlaceSite.md)|Un pointeur vers un pointeur d'interface de [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), d' [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), ou d' [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) du conteneur.|  
|[CComControlBase::m\_spOleAdviseHolder](../Topic/CComControlBase::m_spOleAdviseHolder.md)|Fournit une implémentation standard d'un moyen de stocker les connexions consultatives.|  
  
## Notes  
 Cette classe fournit des méthodes pour créer et gérer des contrôles ATL.  [classe de CComControl](../../atl/reference/ccomcontrol-class.md) dérive d' `CComControlBase`.  Lorsque vous créez un contrôle standard ou le contrôle DHTML à l'aide de l'Assistant Contrôle ATL, l'assistant dérivera automatiquement votre classe d' `CComControlBase`.  
  
 Pour plus d'informations sur la création d'un contrôle, consultez [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md).  Pour plus d'informations sur l'Assistant Projet ATL, consultez l'article [Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md).  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)