---
title: "COleClientItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleClientItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "client items and OLE containers"
  - "COleClientItem class"
  - "container interface class"
  - "OLE client item class"
  - "OLE containers, client items"
  - "OLE containers, classe interface"
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleClientItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l'interface de conteneur à OLE éléments.  
  
## Syntaxe  
  
```  
class COleClientItem : public CDocItem  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleClientItem::COleClientItem](../Topic/COleClientItem::COleClientItem.md)|Construit un objet `COleClientItem`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleClientItem::Activate](../Topic/COleClientItem::Activate.md)|Ouvre un élément OLE pour une opération puis exécute le verbe spécifié.|  
|[COleClientItem::ActivateAs](../Topic/COleClientItem::ActivateAs.md)|Active l'élément comme un autre type.|  
|[COleClientItem::AttachDataObject](../Topic/COleClientItem::AttachDataObject.md)|Accède aux données dans l'objet OLE.|  
|[COleClientItem::CanCreateFromData](../Topic/COleClientItem::CanCreateFromData.md)|Indique si une application conteneur peut créer un objet incorporé.|  
|[COleClientItem::CanCreateLinkFromData](../Topic/COleClientItem::CanCreateLinkFromData.md)|Indique si une application conteneur peut créer un objet lié.|  
|[COleClientItem::CanPaste](../Topic/COleClientItem::CanPaste.md)|Indique si le presse\-papiers contient un élément OLE encastrable ou statique.|  
|[COleClientItem::CanPasteLink](../Topic/COleClientItem::CanPasteLink.md)|Indique si le presse\-papiers contient un élément OLE liable.|  
|[COleClientItem::Close](../Topic/COleClientItem::Close.md)|Ferme un lien vers un serveur mais ne supprime pas le élément OLE.|  
|[COleClientItem::ConvertTo](../Topic/COleClientItem::ConvertTo.md)|Convertit l'élément vers un autre type.|  
|[COleClientItem::CopyToClipboard](../Topic/COleClientItem::CopyToClipboard.md)|Copie le élément OLE dans le presse\-papiers.|  
|[COleClientItem::CreateCloneFrom](../Topic/COleClientItem::CreateCloneFrom.md)|Crée un doublon d'un élément existant.|  
|[COleClientItem::CreateFromClipboard](../Topic/COleClientItem::CreateFromClipboard.md)|Crée un élément incorporé dans le presse\-papiers.|  
|[COleClientItem::CreateFromData](../Topic/COleClientItem::CreateFromData.md)|Crée un élément incorporé d'un objet de données.|  
|[COleClientItem::CreateFromFile](../Topic/COleClientItem::CreateFromFile.md)|Crée un élément inline à partir d'un fichier.|  
|[COleClientItem::CreateLinkFromClipboard](../Topic/COleClientItem::CreateLinkFromClipboard.md)|Crée un élément lié dans le presse\-papiers.|  
|[COleClientItem::CreateLinkFromData](../Topic/COleClientItem::CreateLinkFromData.md)|Crée un élément lié à un objet de données.|  
|[COleClientItem::CreateLinkFromFile](../Topic/COleClientItem::CreateLinkFromFile.md)|Crée un élément lié à partir d'un fichier.|  
|[COleClientItem::CreateNewItem](../Topic/COleClientItem::CreateNewItem.md)|Crée un élément incorporé en activant l'application serveur.|  
|[COleClientItem::CreateStaticFromClipboard](../Topic/COleClientItem::CreateStaticFromClipboard.md)|Crée un élément statique du presse\-papiers.|  
|[COleClientItem::CreateStaticFromData](../Topic/COleClientItem::CreateStaticFromData.md)|Crée un élément statique d'un objet de données.|  
|[COleClientItem::Deactivate](../Topic/COleClientItem::Deactivate.md)|Place l'élément.|  
|[COleClientItem::DeactivateUI](../Topic/COleClientItem::DeactivateUI.md)|Restaure l'interface utilisateur de l'application conteneur à son état d'origine.|  
|[COleClientItem::Delete](../Topic/COleClientItem::Delete.md)|Supprime ou ferme le OLE rubrique s'il s'agissait d'un élément lié.|  
|[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)|Effectue une opération de glisser\-déplacer.|  
|[COleClientItem::DoVerb](../Topic/COleClientItem::DoVerb.md)|Exécute le verbe spécifié.|  
|[COleClientItem::Draw](../Topic/COleClientItem::Draw.md)|Dessine un élément OLE.|  
|[COleClientItem::GetActiveView](../Topic/COleClientItem::GetActiveView.md)|Obtient la vue dans laquelle l'élément est activé en place.|  
|[COleClientItem::GetCachedExtent](../Topic/COleClientItem::GetCachedExtent.md)|Retourne les limites du rectangle OLE de l'élément.|  
|[COleClientItem::GetClassID](../Topic/COleClientItem::GetClassID.md)|Obtient l'ID de la classe de l'élément actuel|  
|[COleClientItem::GetClipboardData](../Topic/COleClientItem::GetClipboardData.md)|Obtient les données qui seraient placées dans le presse\-papiers en appelant la fonction membre d' `CopyToClipboard` .|  
|[COleClientItem::GetDocument](../Topic/COleClientItem::GetDocument.md)|Retourne l'objet d' `COleDocument` qui contient l'élément actuel.|  
|[COleClientItem::GetDrawAspect](../Topic/COleClientItem::GetDrawAspect.md)|Obtient l'affichage actuel de l'élément pour le rendu.|  
|[COleClientItem::GetExtent](../Topic/COleClientItem::GetExtent.md)|Retourne les limites du rectangle OLE de l'élément.|  
|[COleClientItem::GetIconFromRegistry](../Topic/COleClientItem::GetIconFromRegistry.md)|Retrives un handle à une icône associée au serveur CLSID particulier.|  
|[COleClientItem::GetIconicMetafile](../Topic/COleClientItem::GetIconicMetafile.md)|Obtient le métafichier utilisé pour dessiner l'icône de l'élément.|  
|[COleClientItem::GetInPlaceWindow](../Topic/COleClientItem::GetInPlaceWindow.md)|Retourne un pointeur vers la fenêtre de la modification sur place de l'élément.|  
|[COleClientItem::GetItemState](../Topic/COleClientItem::GetItemState.md)|Obtient l'état actuel de l'élément.|  
|[COleClientItem::GetLastStatus](../Topic/COleClientItem::GetLastStatus.md)|Retourne l'état de la dernière exécution. OLE|  
|[COleClientItem::GetLinkUpdateOptions](../Topic/COleClientItem::GetLinkUpdateOptions.md)|Retourne le mode mise à jour d'un élément lié \(fonctionnalité avancée\).|  
|[COleClientItem::GetType](../Topic/COleClientItem::GetType.md)|Retourne le type \(incorporé, attaché, ou statique\) du élément OLE.|  
|[COleClientItem::GetUserType](../Topic/COleClientItem::GetUserType.md)|Obtient une chaîne décrivant le type de l'élément.|  
|[COleClientItem::IsInPlaceActive](../Topic/COleClientItem::IsInPlaceActive.md)|Retourne `TRUE` si l'élément est actif sur place.|  
|[COleClientItem::IsLinkUpToDate](../Topic/COleClientItem::IsLinkUpToDate.md)|Retourne **TRUE** si un élément est lié à jour avec son document source.|  
|[COleClientItem::IsModified](../Topic/COleClientItem::IsModified.md)|Retourne `TRUE` si l'élément a été modifié depuis lequel il a été en dernier enregistrement.|  
|[COleClientItem::IsOpen](../Topic/COleClientItem::IsOpen.md)|Retourne `TRUE` si l'élément est ouvert dans l'application serveur.|  
|[COleClientItem::IsRunning](../Topic/COleClientItem::IsRunning.md)|Retourne `TRUE` si l'application serveur de l'élément s'exécute.|  
|[COleClientItem::OnActivate](../Topic/COleClientItem::OnActivate.md)|Appelé par l'infrastructure pour informer l'élément qu'il est activé.|  
|[COleClientItem::OnActivateUI](../Topic/COleClientItem::OnActivateUI.md)|Appelé par l'infrastructure pour informer l'élément qu'il est lancé et doit afficher son interface utilisateur.|  
|[COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md)|Appelé lorsque le serveur modifie le élément OLE.  Implémentation requise.|  
|[COleClientItem::OnDeactivate](../Topic/COleClientItem::OnDeactivate.md)|Appelé par l'infrastructure lorsqu'un élément est désactivé.|  
|[COleClientItem::OnDeactivateUI](../Topic/COleClientItem::OnDeactivateUI.md)|Appelé par l'infrastructure lorsque le serveur a supprimé son interface utilisateur visuelle.|  
|[COleClientItem::OnGetClipboardData](../Topic/COleClientItem::OnGetClipboardData.md)|Appelé par l'infrastructure pour obtenir les données soient copiés dans le presse\-papiers.|  
|[COleClientItem::OnInsertMenus](../Topic/COleClientItem::OnInsertMenus.md)|Appelé par l'infrastructure pour créer un menu composite.|  
|[COleClientItem::OnRemoveMenus](../Topic/COleClientItem::OnRemoveMenus.md)|Appelé par l'infrastructure pour supprimer les menus du conteneur d'un menu composite.|  
|[COleClientItem::OnSetMenu](../Topic/COleClientItem::OnSetMenu.md)|Appelé par l'infrastructure pour installer et supprimer un menu composite.|  
|[COleClientItem::OnShowControlBars](../Topic/COleClientItem::OnShowControlBars.md)|Appelé par l'infrastructure pour afficher et masquer des barres de contrôles.|  
|[COleClientItem::OnUpdateFrameTitle](../Topic/COleClientItem::OnUpdateFrameTitle.md)|Appelé par l'infrastructure pour mettre à jour la barre de titre de la fenêtre frame.|  
|[COleClientItem::ReactivateAndUndo](../Topic/COleClientItem::ReactivateAndUndo.md)|Réactive l'élément et annule la dernière opération de modification sur place.|  
|[COleClientItem::Release](../Topic/COleClientItem::Release.md)|Libère la connexion à un élément OLE lié et la batterie si elle a été ouverte.  Ne supprime pas l'élément client.|  
|[COleClientItem::Reload](../Topic/COleClientItem::Reload.md)|Recharge l'élément après un appel à `ActivateAs`.|  
|[COleClientItem::Run](../Topic/COleClientItem::Run.md)|Exécute l'application associée à l'élément.|  
|[COleClientItem::SetDrawAspect](../Topic/COleClientItem::SetDrawAspect.md)|Définit l'affichage actuel de l'élément pour le rendu.|  
|[COleClientItem::SetExtent](../Topic/COleClientItem::SetExtent.md)|Définit le rectangle englobant d'un élément OLE.|  
|[COleClientItem::SetHostNames](../Topic/COleClientItem::SetHostNames.md)|Définit les noms que le serveur affiche en modifiant le élément OLE.|  
|[COleClientItem::SetIconicMetafile](../Topic/COleClientItem::SetIconicMetafile.md)|Met en cache le métafichier utilisé pour dessiner l'icône de l'élément.|  
|[COleClientItem::SetItemRects](../Topic/COleClientItem::SetItemRects.md)|Définit le rectangle englobant de l'élément.|  
|[COleClientItem::SetLinkUpdateOptions](../Topic/COleClientItem::SetLinkUpdateOptions.md)|Définit le mode mise à jour d'un élément lié \(fonctionnalité avancée\).|  
|[COleClientItem::SetPrintDevice](../Topic/COleClientItem::SetPrintDevice.md)|Définit le périphérique de copie\- cible pour cet élément client.|  
|[COleClientItem::UpdateLink](../Topic/COleClientItem::UpdateLink.md)|Met à jour le cache de présentation d'un élément.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleClientItem::CanActivate](../Topic/COleClientItem::CanActivate.md)|Appelé par l'infrastructure pour déterminer si l'activation sur place.|  
|[COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)|Appelé par l'infrastructure lorsque la position d'un élément change.|  
|[COleClientItem::OnDeactivateAndUndo](../Topic/COleClientItem::OnDeactivateAndUndo.md)|Appelé par l'infrastructure pour l'annulation après l'activation.|  
|[COleClientItem::OnDiscardUndoState](../Topic/COleClientItem::OnDiscardUndoState.md)|Appelé par l'infrastructure pour ignorer les informations d'état d'annulation de l'élément.|  
|[COleClientItem::OnGetClipRect](../Topic/COleClientItem::OnGetClipRect.md)|Appelé par l'infrastructure pour obtenir les coordonnées du rectangle de découpage de l'élément.|  
|[COleClientItem::OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)|Appelé par l'infrastructure pour obtenir la position de l'élément par rapport à la vue.|  
|[COleClientItem::OnGetWindowContext](../Topic/COleClientItem::OnGetWindowContext.md)|Appelé par l'infrastructure lorsqu'un élément est activé en place.|  
|[COleClientItem::OnScrollBy](../Topic/COleClientItem::OnScrollBy.md)|Appelé par l'infrastructure pour faire défiler l'élément dans la vue.|  
|[COleClientItem::OnShowItem](../Topic/COleClientItem::OnShowItem.md)|Appelé par l'infrastructure pour afficher un élément OLE.|  
  
## Notes  
 Un élément OLE représente des données, créées et mises à jour par une application serveur, qui peut être «  » de façon transparente incorporée dans un document afin qu'elle semble à l'utilisateur être un document unique.  Le résultat est un « document composite » composé d'un élément OLE et d'un document contenant.  
  
 Un élément OLE peut être inclus ou lié.  S'il est incorporé, ses données sont stockées dans le cadre de le document composite.  Si elles sont attachées, ses données sont stockées dans le cadre d'un fichier séparé créé par l'application serveur, ainsi qu'un lien vers ce fichier est stocké dans le document composite.  Tous les éléments OLE contiennent des informations spécifiant l'application serveur qui doit être appelée pour les modifier.  
  
 `COleClientItem` définit plusieurs fonctions substituables qui sont appelées en réponse à les demandes de l'application serveur ; ces overridables interagissent généralement comme notifications.  Cela permet à l'application serveur d'informer le conteneur de modifications que l'utilisateur effectue en modifiant le élément OLE, ou d'extraire les informations requises lors de la modification.  
  
 `COleClientItem` peut être utilisé avec la classe de [COleDocument](../../mfc/reference/coledocument-class.md), de [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), ou de [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) .  Pour utiliser `COleClientItem`, dérivez une classe de celle\-ci et implémentez la fonction membre d' [OnChange](../Topic/COleClientItem::OnChange.md) , qui définit comment le conteneur répond aux modifications apportées à l'élément.  Pour prendre en charge l'activation sur place, substituez la fonction membre d' [OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md) .  Cette fonction fournit des informations sur la position affichée du élément OLE.  
  
 Pour plus d'informations sur l'utilisation de l'interface de conteneur, consultez les articles [conteneurs : implémenter un conteneur](../../mfc/containers-implementing-a-container.md) et [lancement](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] fait référence incorporé et des éléments liés comme « objets et » fait référence aux types d'éléments en tant que « classe ». Les utilisations de cette référence le terme « élément » de distinguer OLE entité de l'objet correspondant C\+\+ et le terme « type » pour distinguer OLE catégorie de la classe C\+\+.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [MFC exemple MFCBIND](../../top/visual-cpp-samples.md)   
 [exemple MFC OCLIENT](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)