---
title: "COleControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControl class"
  - "controls [MFC], OLE"
  - "controls [MFC], windowless"
  - "contrôles OLE, MFC"
  - "windowless controls"
  - "windowless controls, MFC"
ms.assetid: 53e95299-38e8-447b-9c5f-a381d27f5123
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# COleControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe de base puissante pour développer des contrôles OLE.  
  
## Syntaxe  
  
```  
class COleControl : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControl::COleControl](../Topic/COleControl::COleControl.md)|Crée un objet `COleControl`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControl::AmbientAppearance](../Topic/COleControl::AmbientAppearance.md)|Récupère l'apparence actuelle du contrôle.|  
|[COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)|Retourne la valeur de la propriété ambiante BackColor.|  
|[COleControl::AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)|Retourne le nom du contrôle comme spécifié par le conteneur.|  
|[COleControl::AmbientFont](../Topic/COleControl::AmbientFont.md)|Retourne la valeur de la propriété Font ambiante.|  
|[COleControl::AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)|Retourne la valeur de la propriété ambiante de ForeColor.|  
|[COleControl::AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)|Retourne l'ID de paramètres régionaux du conteneur|  
|[COleControl::AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)|Retourne le type d'unités utilisées par le conteneur.|  
|[COleControl::AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)|Détermine si les poignées de manipulation sont affichés.|  
|[COleControl::AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)|Détermine si la marque de hachage est affichée.|  
|[COleControl::AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)|Retourne le type d'alignement de texte spécifié par le conteneur.|  
|[COleControl::AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)|Détermine si le contrôle répond aux actions d'interface utilisateur.|  
|[COleControl::AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)|Détermine le mode du conteneur.|  
|[COleControl::BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md)|Informe le conteneur qu'une propriété liée a été modifiée.|  
|[COleControl::BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md)|Demande l'autorisation de modifier la valeur de propriété.|  
|[COleControl::ClientToParent](../Topic/COleControl::ClientToParent.md)|Convertit un point par rapport à l'origine du contrôle à un point par rapport à l'origine de son conteneur.|  
|[COleControl::ClipCaretRect](../Topic/COleControl::ClipCaretRect.md)|Règle un rectangle de signe insertion s'il est chevauché par un contrôle.|  
|[COleControl::ControlInfoChanged](../Topic/COleControl::ControlInfoChanged.md)|Appelez cette fonction après que l'ensemble des mnémoniques gérée par le contrôle a changé.|  
|[COleControl::DisplayError](../Topic/COleControl::DisplayError.md)|Les affichages stockent des événements d'erreur à l'utilisateur du contrôle.|  
|[COleControl::DoClick](../Topic/COleControl::DoClick.md)|Implémentation de la méthode magasin d' `DoClick` .|  
|[COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)|Sérialise les propriétés d'un objet d' `COleControl` .|  
|[COleControl::DoSuperclassPaint](../Topic/COleControl::DoSuperclassPaint.md)|Redessine un contrôle OLE qui a été sous\-classé d'un contrôle Windows.|  
|[COleControl::EnableSimpleFrame](../Topic/COleControl::EnableSimpleFrame.md)|Permet la prise en charge simple de frame d'un contrôle.|  
|[COleControl::ExchangeExtent](../Topic/COleControl::ExchangeExtent.md)|Sérialise la largeur et la hauteur du contrôle.|  
|[COleControl::ExchangeStockProps](../Topic/COleControl::ExchangeStockProps.md)|Sérialise les propriétés des actions du contrôle.|  
|[COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md)|Sérialise le numéro de version du contrôle.|  
|[COleControl::FireClick](../Topic/COleControl::FireClick.md)|Déclenche l'événement magasin d' `Click` .|  
|[COleControl::FireDblClick](../Topic/COleControl::FireDblClick.md)|Déclenche l'événement magasin d' `DblClick` .|  
|[COleControl::FireError](../Topic/COleControl::FireError.md)|Déclenche l'événement magasin d' `Error` .|  
|[COleControl::FireEvent](../Topic/COleControl::FireEvent.md)|Déclenche un événement personnalisé.|  
|[COleControl::FireKeyDown](../Topic/COleControl::FireKeyDown.md)|Déclenche l'événement magasin d' `KeyDown` .|  
|[COleControl::FireKeyPress](../Topic/COleControl::FireKeyPress.md)|Déclenche l'événement magasin d' `KeyPress` .|  
|[COleControl::FireKeyUp](../Topic/COleControl::FireKeyUp.md)|Déclenche l'événement magasin d' `KeyUp` .|  
|[COleControl::FireMouseDown](../Topic/COleControl::FireMouseDown.md)|Déclenche l'événement magasin d' `MouseDown` .|  
|[COleControl::FireMouseMove](../Topic/COleControl::FireMouseMove.md)|Déclenche l'événement magasin d' `MouseMove` .|  
|[COleControl::FireMouseUp](../Topic/COleControl::FireMouseUp.md)|Déclenche l'événement magasin d' `MouseUp` .|  
|[COleControl::FireReadyStateChange](../Topic/COleControl::FireReadyStateChange.md)|Déclenche un événement lorsque les modifications d'état prêt du contrôle.|  
|[COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md)|Modifie le comportement par défaut de l'activation d'un contrôle qui prend en charge l'interface d' `IPointerInactive` .|  
|[COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md)|Retourne la valeur de la propriété ambiante spécifiée.|  
|[COleControl::GetAppearance](../Topic/COleControl::GetAppearance.md)|Retourne la valeur de la propriété d'apparence boursières.|  
|[COleControl::GetBackColor](../Topic/COleControl::GetBackColor.md)|Retourne la valeur de la propriété stock BackColor.|  
|[COleControl::GetBorderStyle](../Topic/COleControl::GetBorderStyle.md)|Retourne la valeur de la propriété boursières de BorderStyle.|  
|[COleControl::GetCapture](../Topic/COleControl::GetCapture.md)|Détermine si un objet de contrôles sans fenêtre et a activé la capture de la souris.|  
|[COleControl::GetClassID](../Topic/COleControl::GetClassID.md)|Récupère l'ID de classe OLE du contrôle.|  
|[COleControl::GetClientOffset](../Topic/COleControl::GetClientOffset.md)|Extrait la différence entre l'angle supérieur gauche de la zone rectangulaire du contrôle et le coin supérieur gauche de sa zone cliente.|  
|[COleControl::GetClientRect](../Topic/COleControl::GetClientRect.md)|Extrait la taille de la zone cliente du contrôle.|  
|[COleControl::GetClientSite](../Topic/COleControl::GetClientSite.md)|Interroge un objet pour le pointeur à son site client actuel dans son conteneur.|  
|[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)|Récupère les paramètres de balise de contrôle.|  
|[COleControl::GetControlSize](../Topic/COleControl::GetControlSize.md)|Retourne la position et la taille du contrôle OLE.|  
|[COleControl::GetDC](../Topic/COleControl::GetDC.md)|Fournit un moyen pour un contrôle sans fenêtre obtenir un contexte de périphérique de son conteneur.|  
|[COleControl::GetEnabled](../Topic/COleControl::GetEnabled.md)|Retourne la valeur de la propriété Enabled boursières.|  
|[COleControl::GetExtendedControl](../Topic/COleControl::GetExtendedControl.md)|Extrait un pointeur vers un objet contrôle étendu appartenant au conteneur.|  
|[COleControl::GetFocus](../Topic/COleControl::GetFocus.md)|Détermine si le contrôle a le focus.|  
|[COleControl::GetFont](../Topic/COleControl::GetFont.md)|Retourne la valeur de la propriété stock Font.|  
|[COleControl::GetFontTextMetrics](../Topic/COleControl::GetFontTextMetrics.md)|Retourne la métrique d'un objet d' `CFontHolder` .|  
|[COleControl::GetForeColor](../Topic/COleControl::GetForeColor.md)|Retourne la valeur de la propriété de stock ForeColor.|  
|[COleControl::GetHwnd](../Topic/COleControl::GetHwnd.md)|Retourne la valeur de la propriété boursières de hWnd.|  
|[COleControl::GetMessageString](../Topic/COleControl::GetMessageString.md)|Fournit le texte de la barre d'état d'un élément de menu.|  
|[COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md)|Empêché l'accès à la valeur de propriété d'un contrôle par l'utilisateur.|  
|[COleControl::GetReadyState](../Topic/COleControl::GetReadyState.md)|Retourne l'état de la disponibilité du contrôle.|  
|[COleControl::GetRectInContainer](../Topic/COleControl::GetRectInContainer.md)|Retourne le rectangle du contrôle par rapport à son conteneur.|  
|[COleControl::GetStockTextMetrics](../Topic/COleControl::GetStockTextMetrics.md)|Retourne la métrique de propriétés stock Font.|  
|[COleControl::GetText](../Topic/COleControl::GetText.md)|Retourne la valeur de la propriété magasin de texte ou de légende.|  
|[COleControl::GetWindowlessDropTarget](../Topic/COleControl::GetWindowlessDropTarget.md)|Substitution pour permettre à un contrôle sans fenêtre à être la cible les opérations de glisser\-déplacer.|  
|[COleControl::InitializeIIDs](../Topic/COleControl::InitializeIIDs.md)|Notifie la classe de base des IID que le contrôle utilisera.|  
|[COleControl::InternalGetFont](../Topic/COleControl::InternalGetFont.md)|Retourne un objet d' `CFontHolder` pour la propriété stock Font.|  
|[COleControl::InternalGetText](../Topic/COleControl::InternalGetText.md)|Extrait la légende ou la propriété Text boursières.|  
|[COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md)|Définit l'état de la disponibilité du contrôle et déclenche l'événement de prêt\-état\- modification.|  
|[COleControl::InvalidateControl](../Topic/COleControl::InvalidateControl.md)|Invalide un domaine du contrôle affiché, le causant d'être redessiné.|  
|[COleControl::InvalidateRgn](../Topic/COleControl::InvalidateRgn.md)|Invalide la zone cliente de la fenêtre de conteneur dans la zone donnée.  Peut être utilisé pour redessiner des contrôles sans fenêtre dans une région.|  
|[COleControl::IsConvertingVBX](../Topic/COleControl::IsConvertingVBX.md)|Allows un spécialisé le chargement d'un contrôle OLE.|  
|[COleControl::IsModified](../Topic/COleControl::IsModified.md)|Détermine si l'état du contrôle a changé.|  
|[COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md)|Indique si le conteneur en charge le dessin optimisé pour l'exécution actuelle de dessin.|  
|[COleControl::IsSubclassedControl](../Topic/COleControl::IsSubclassedControl.md)|Appelé pour déterminer si les sous\-classes d'un contrôle Windows.|  
|[COleControl::Load](../Topic/COleControl::Load.md)|Réinitialise toutes les données asynchrones précédentes et initialise un nouveau charge de la propriété asynchrone du contrôle.|  
|[COleControl::LockInPlaceActive](../Topic/COleControl::LockInPlaceActive.md)|Détermine si votre contrôle peut être désactivé par le conteneur.|  
|[COleControl::OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md)|Appelé lorsqu'une propriété ambiante est modifiée.|  
|[COleControl::OnAppearanceChanged](../Topic/COleControl::OnAppearanceChanged.md)|Appelé lorsque la propriété d'apparence stock est modifiée.|  
|[COleControl::OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md)|Appelé lorsque la propriété BackColor d'actions est modifiée.|  
|[COleControl::OnBorderStyleChanged](../Topic/COleControl::OnBorderStyleChanged.md)|Appelé lorsque la propriété de BorderStyle d'actions est modifiée.|  
|[COleControl::OnClick](../Topic/COleControl::OnClick.md)|Appelé pour déclencher l'événement clic du stock.|  
|[COleControl::OnClose](../Topic/COleControl::OnClose.md)|Informe le contrôle qu' `IOleControl::Close` a été appelé.|  
|[COleControl::OnDoVerb](../Topic/COleControl::OnDoVerb.md)|Appelé après qu'un verbe de contrôle a été exécuté.|  
|[COleControl::OnDraw](../Topic/COleControl::OnDraw.md)|Appelé lorsqu'un contrôle est demandé se repeindre.|  
|[COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md)|Appelé par le conteneur lorsqu'un contrôle est demandé se repeindre avec un contexte de périphérique de métafichier.|  
|[COleControl::OnEdit](../Topic/COleControl::OnEdit.md)|Appelé par le conteneur à l'interface utilisateur d'activer un contrôle OLE.|  
|[COleControl::OnEnabledChanged](../Topic/COleControl::OnEnabledChanged.md)|Appelé lorsque la propriété Enabled stock est modifiée.|  
|[COleControl::OnEnumVerbs](../Topic/COleControl::OnEnumVerbs.md)|Appelé par le conteneur pour énumérer les verbes d'un contrôle.|  
|[COleControl::OnEventAdvise](../Topic/COleControl::OnEventAdvise.md)|Appelée lorsque les gestionnaires d'événements sont connectés ou déconnectés d'un contrôle.|  
|[COleControl::OnFontChanged](../Topic/COleControl::OnFontChanged.md)|Appelé lorsque la propriété du stock Font est modifiée.|  
|[COleControl::OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md)|Appelé lorsque la propriété de ForeColor d'actions est modifiée.|  
|[COleControl::OnFreezeEvents](../Topic/COleControl::OnFreezeEvents.md)|Appelée lorsque les événements d'un contrôle sont figés ou dégelés.|  
|[COleControl::OnGetColorSet](../Topic/COleControl::OnGetColorSet.md)|Informe le contrôle qu' `IOleObject::GetColorSet` a été appelé.|  
|[COleControl::OnGetControlInfo](../Topic/COleControl::OnGetControlInfo.md)|Fournit des informations mnémoniques au conteneur.|  
|[COleControl::OnGetDisplayString](../Topic/COleControl::OnGetDisplayString.md)|Appelé pour obtenir une chaîne représentant une valeur de propriété.|  
|[COleControl::OnGetInPlaceMenu](../Topic/COleControl::OnGetInPlaceMenu.md)|Demande le handle du menu de contrôle qui sera fusionné avec le menu du conteneur.|  
|[COleControl::OnGetNaturalExtent](../Topic/COleControl::OnGetNaturalExtent.md)|Substitution pour récupérer la taille d'affichage du contrôle la plus proche du mode proposé de taille et d'étendue.|  
|[COleControl::OnGetPredefinedStrings](../Topic/COleControl::OnGetPredefinedStrings.md)|Retourne des chaînes représentant les valeurs possibles pour une propriété.|  
|[COleControl::OnGetPredefinedValue](../Topic/COleControl::OnGetPredefinedValue.md)|Retourne la valeur correspondant à une chaîne prédéfinie.|  
|[COleControl::OnGetViewExtent](../Topic/COleControl::OnGetViewExtent.md)|Substitution pour récupérer la taille des zones d'affichage du contrôle \(peut être utilisé pour activer le dessin de deux exécution\).|  
|[COleControl::OnGetViewRect](../Topic/COleControl::OnGetViewRect.md)|Substitution pour convertir la taille du contrôle dans un rectangle en commençant à un emplacement spécifique.|  
|[COleControl::OnGetViewStatus](../Topic/COleControl::OnGetViewStatus.md)|Substitution pour récupérer le mode de la vue du contrôle.|  
|[COleControl::OnHideToolBars](../Topic/COleControl::OnHideToolBars.md)|Appelé par le conteneur lorsque le contrôle est interface utilisateur désactivé.|  
|[COleControl::OnInactiveMouseMove](../Topic/COleControl::OnInactiveMouseMove.md)|Substitution pour que le conteneur du contrôle inactif sous les messages d' `WM_MOUSEMOVE` de dispatch du pointeur de la souris au contrôle.|  
|[COleControl::OnInactiveSetCursor](../Topic/COleControl::OnInactiveSetCursor.md)|Substitution pour que le conteneur du contrôle inactif sous les messages d' `WM_SETCURSOR` de dispatch du pointeur de la souris au contrôle.|  
|[COleControl::OnKeyDownEvent](../Topic/COleControl::OnKeyDownEvent.md)|Appelé après l'événement KeyDown d'actions a été déclenché.|  
|[COleControl::OnKeyPressEvent](../Topic/COleControl::OnKeyPressEvent.md)|Appelé après l'événement KeyPress d'actions a été déclenché.|  
|[COleControl::OnKeyUpEvent](../Topic/COleControl::OnKeyUpEvent.md)|Appelé après l'événement de KeyUp d'actions a été déclenché.|  
|[COleControl::OnMapPropertyToPage](../Topic/COleControl::OnMapPropertyToPage.md)|Indique que la page de propriétés à utiliser pour modifier une propriété.|  
|[COleControl::OnMnemonic](../Topic/COleControl::OnMnemonic.md)|Appelé lorsqu'une touche mnémonique du contrôle a été enfoncée.|  
|[COleControl::OnProperties](../Topic/COleControl::OnProperties.md)|Appelé lorsque le verbe des « properties » du contrôle a été appelé.|  
|[COleControl::OnQueryHitPoint](../Topic/COleControl::OnQueryHitPoint.md)|Substitution à interroger si l'affichage d'un contrôle chevauche un point donné.|  
|[COleControl::OnQueryHitRect](../Topic/COleControl::OnQueryHitRect.md)|Substitution à interroger si l'affichage d'un contrôle chevauche tout point dans un rectangle donné.|  
|[COleControl::OnRenderData](../Topic/COleControl::OnRenderData.md)|Appelé par l'infrastructure pour récupérer des données dans le format spécifié.|  
|[COleControl::OnRenderFileData](../Topic/COleControl::OnRenderFileData.md)|Appelé par l'infrastructure pour récupérer des données à partir d'un fichier au format spécifié.|  
|[COleControl::OnRenderGlobalData](../Topic/COleControl::OnRenderGlobalData.md)|Appelé par l'infrastructure pour récupérer les données de mémoire globale dans le format spécifié.|  
|[COleControl::OnResetState](../Topic/COleControl::OnResetState.md)|Réinitialise les propriétés d'un contrôle aux valeurs par défaut.|  
|[COleControl::OnSetClientSite](../Topic/COleControl::OnSetClientSite.md)|Informe le contrôle qu' `IOleControl::SetClientSite` a été appelé.|  
|[COleControl::OnSetData](../Topic/COleControl::OnSetData.md)|Remplace les paramètres par une autre valeur.|  
|[COleControl::OnSetExtent](../Topic/COleControl::OnSetExtent.md)|Appelé après l'étendue du contrôle a changé.|  
|[COleControl::OnSetObjectRects](../Topic/COleControl::OnSetObjectRects.md)|Appelé après les dimensions du contrôle ont été changés.|  
|[COleControl::OnShowToolBars](../Topic/COleControl::OnShowToolBars.md)|Appelé lorsque le contrôle a été interface utilisateur activé.|  
|[COleControl::OnTextChanged](../Topic/COleControl::OnTextChanged.md)|Appelé lorsque la propriété magasin de texte ou de légende est modifiée.|  
|[COleControl::OnWindowlessMessage](../Topic/COleControl::OnWindowlessMessage.md)|Traite les messages de fenêtre \(autre que les messages de clavier et de souris\) pour les contrôles sans fenêtre.|  
|[COleControl::ParentToClient](../Topic/COleControl::ParentToClient.md)|Convertit un point par rapport à l'origine du conteneur à un point par rapport à l'origine du contrôle.|  
|[COleControl::PostModalDialog](../Topic/COleControl::PostModalDialog.md)|Informe le conteneur qu'une boîte de dialogue modale a été fermée.|  
|[COleControl::PreModalDialog](../Topic/COleControl::PreModalDialog.md)|Informe le conteneur qu'une boîte de dialogue modale est sur le point d'être affiché.|  
|[COleControl::RecreateControlWindow](../Topic/COleControl::RecreateControlWindow.md)|Détruit et recrée la fenêtre du contrôle.|  
|[COleControl::Refresh](../Topic/COleControl::Refresh.md)|Force un redessiner de l'apparence d'un contrôle.|  
|[COleControl::ReleaseCapture](../Topic/COleControl::ReleaseCapture.md)|Libère la capture de la souris.|  
|[COleControl::ReleaseDC](../Topic/COleControl::ReleaseDC.md)|Libère le contexte de périphérique d'affichage d'un conteneur d'un contrôle sans fenêtre.|  
|[COleControl::ReparentControlWindow](../Topic/COleControl::ReparentControlWindow.md)|Réinitialise le parent de la fenêtre du contrôle.|  
|[COleControl::ResetStockProps](../Topic/COleControl::ResetStockProps.md)|Initialise les propriétés d'actions d' `COleControl` à leurs valeurs par défaut.|  
|[COleControl::ResetVersion](../Topic/COleControl::ResetVersion.md)|Initialise le numéro de version à une valeur donnée.|  
|[COleControl::ScrollWindow](../Topic/COleControl::ScrollWindow.md)|Permet à un contrôle sans fenêtre pour faire défiler une zone dans son image active sur place de l'affichage.|  
|[COleControl::SelectFontObject](../Topic/COleControl::SelectFontObject.md)|Sélectionne une propriété Font personnalisée dans un contexte de périphérique.|  
|[COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md)|Sélectionne la propriété stock Font dans un contexte de périphérique.|  
|[COleControl::SerializeExtent](../Topic/COleControl::SerializeExtent.md)|Sérialise ou initialise l'espace d'affichage du contrôle.|  
|[COleControl::SerializeStockProps](../Topic/COleControl::SerializeStockProps.md)|Sérialise ou initialise les propriétés d'actions d' `COleControl` .|  
|[COleControl::SerializeVersion](../Topic/COleControl::SerializeVersion.md)|Sérialise ou initialise les informations de version du contrôle.|  
|[COleControl::SetAppearance](../Topic/COleControl::SetAppearance.md)|Définit la valeur de la propriété d'apparence boursières.|  
|[COleControl::SetBackColor](../Topic/COleControl::SetBackColor.md)|Définit la valeur de la propriété stock BackColor.|  
|[COleControl::SetBorderStyle](../Topic/COleControl::SetBorderStyle.md)|Définit la valeur de la propriété boursières de BorderStyle.|  
|[COleControl::SetCapture](../Topic/COleControl::SetCapture.md)|Pour prendre la fenêtre de conteneur du contrôle la propriétaire de la capture de la souris sur le nom du contrôle.|  
|[COleControl::SetControlSize](../Topic/COleControl::SetControlSize.md)|Définit la position et la taille du contrôle OLE.|  
|[COleControl::SetEnabled](../Topic/COleControl::SetEnabled.md)|Définit la valeur de la propriété Enabled boursières.|  
|[COleControl::SetFocus](../Topic/COleControl::SetFocus.md)|Pour prendre la fenêtre de conteneur du contrôle le propriétaire du focus d'entrée le nom du contrôle.|  
|[COleControl::SetFont](../Topic/COleControl::SetFont.md)|Définit la valeur de la propriété stock Font.|  
|[COleControl::SetForeColor](../Topic/COleControl::SetForeColor.md)|Définit la valeur de la propriété de stock ForeColor.|  
|[COleControl::SetInitialSize](../Topic/COleControl::SetInitialSize.md)|Définit la taille d'un contrôle OLE une fois d'abord affiché dans un conteneur.|  
|[COleControl::SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md)|Modifie l'état modifié d'un contrôle.|  
|[COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md)|Indique qu'une demande de modification a échoué.|  
|[COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md)|Empêché la modification de la valeur de propriété d'un contrôle par l'utilisateur.|  
|[COleControl::SetRectInContainer](../Topic/COleControl::SetRectInContainer.md)|Définit le rectangle du contrôle par rapport à son conteneur.|  
|[COleControl::SetText](../Topic/COleControl::SetText.md)|Définit la valeur de la propriété magasin de texte ou de légende.|  
|[COleControl::ThrowError](../Topic/COleControl::ThrowError.md)|Signale qu'une erreur s'est produite dans un contrôle OLE.|  
|[COleControl::TransformCoords](../Topic/COleControl::TransformCoords.md)|Les transformations coordonnent des valeurs entre un conteneur et.|  
|[COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md)|Convertit une valeur d' **OLE\_COLOR** à une valeur de **COLORREF** .|  
|[COleControl::WillAmbientsBeValidDuringLoad](../Topic/COleControl::WillAmbientsBeValidDuringLoad.md)|Détermine si les propriétés ambiantes soient disponibles la prochaine fois le contrôle est chargé.|  
|[COleControl::WindowProc](../Topic/COleControl::WindowProc.md)|Fournit une procédure de fenêtre pour un objet d' `COleControl` .|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleControl::DrawContent](../Topic/COleControl::DrawContent.md)|Appelé par l'infrastructure lorsque l'apparence du contrôle doit être mise à jour.|  
|[COleControl::DrawMetafile](../Topic/COleControl::DrawMetafile.md)|Appelé par l'infrastructure lorsque le contexte de périphérique de métafichier est utilisé.|  
|[COleControl::IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md)|Active l'appel de méthode automation.|  
|[COleControl::SetInitialDataFormats](../Topic/COleControl::SetInitialDataFormats.md)|Appelé par l'infrastructure pour initialiser la liste de formats de données pris en charge par le contrôle.|  
  
## Notes  
 Dérivé d' `CWnd`, cette classe hérite de toutes les fonctionnalités d'un objet window windows ainsi que le détail de fonctionnalités supplémentaires OLE, tel que le déclenchement d'événements et une fonctionnalité de prendre en charge les méthodes et les propriétés.  
  
 Les contrôles OLE peuvent être insérés dans les applications de conteneur OLE et communiquer avec le conteneur à l'aide d'un système bidirectionnel de déclenchement d'événements et des méthodes pour exposer les propriétés et au conteneur.  Notez que les conteneurs OLE standard prennent uniquement en charge les fonctionnalités de base d'un contrôle OLE.  Ils ne peuvent pas prendre en charge les fonctionnalités étendues d'un contrôle OLE.  Le déclenchement d'événements se produit lorsque les événements sont envoyés au conteneur à la suite de certaines actions ayant lieu dans le contrôle.  Ensuite, le conteneur communique avec le contrôle à l'aide d'un ensemble exposé de méthodes et les propriétés analogues aux fonctions membres et aux membres de données C\+\+ classe.  Cette approche permet au développeur pour contrôler l'apparence du contrôle et pour informer le conteneur lorsque certaines actions se produisent.  
  
## Contrôles sans fenêtre  
 Les contrôles OLE peuvent être actif sur place utilisé sans fenêtre.  Les contrôles sans fenêtre présentent des avantages importants :  
  
-   Les contrôles sans fenêtre peuvent être transparents et non rectangulaires  
  
-   Les contrôles sans fenêtre de réduire la taille d'instance et l'heure de création de l'objet  
  
 Les contrôles n'ont pas besoin d'une fenêtre.  Les services qu'une fenêtre offre peuvent facilement être disponibles via une fenêtre partagée unique \(généralement le conteneur\) et d'un bit de distribuer le code.  Avoir une fenêtre est principalement difficulté une inutile dans l'objet.  
  
 Lorsque l'activation sans fenêtre est utilisé, le conteneur \(qui possède une fenêtre\) permet de fournir des services qui auraient normalement fournis par la propre fenêtre du contrôle.  Par exemple, si votre contrôle doit interroger le focus clavier, d'interroger la capture de la souris, ou pour obtenir un contexte de périphérique, ces opérations sont gérés par le conteneur.  `COleControl`[fonctions membres de sans fenêtres\-exécution](http://msdn.microsoft.com/fr-fr/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) appellent ces opérations sur le conteneur.  
  
 Lorsque l'activation sans fenêtre est activé, le conteneur délègue les messages d'entrée à l'interface d' `IOleInPlaceObjectWindowless` du contrôle \(une extension d' [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) pour la prise en charge sans fenêtre\).  l'implémentation d'`COleControl` de cette interface acheminera ces messages dans la table des messages de votre contrôle, après avoir défini les coordonnées de la souris correctement.  Vous pouvez traiter ces messages comme les messages des fenêtres ordinaires, en ajoutant les entrées correspondantes dans la table des messages.  
  
 Dans un contrôle sans fenêtre, vous devez toujours utiliser les fonctions membres d' `COleControl` à la place des fonctions membres correspondantes d' `CWnd` ou de leurs fonctions API Windows connexes.  
  
 Les objets de contrôle OLE peuvent également créer une fenêtre uniquement lorsqu'ils deviennent actifs, mais la quantité de travail nécessaire à la transition inactif\- active monte et la vitesse de la transition descend.  Dans certains cas lorsqu'il s'agit d'un problème : par exemple, considérez une grille des zones de texte.  Cursoring haut et bas dans la colonne, chaque contrôle doit être activé sur place et ensuite désactivé.  La vitesse de transition inactive\/active affecte directement la vitesse de défilement.  
  
 Pour plus d'informations sur le développement d'une infrastructure de contrôle OLE, consultez les articles [Contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md) et [présentation : créer un programme de contrôle ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).  Pour plus d'informations sur l'optimisation des contrôles OLE, y compris les contrôles sans fenêtre et sans scintillement, consultez [Contrôles ActiveX MFC : optimisation](../../mfc/mfc-activex-controls-optimization.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `COleControl`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [exemple MFC CIRC3](../../top/visual-cpp-samples.md)   
 [exemple MFC TESTHELP](../../top/visual-cpp-samples.md)   
 [COlePropertyPage Class](../../mfc/reference/colepropertypage-class.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)   
 [CPictureHolder Class](../../mfc/reference/cpictureholder-class.md)