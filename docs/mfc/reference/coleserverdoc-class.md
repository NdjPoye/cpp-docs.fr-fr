---
title: "COleServerDoc Class | Microsoft Docs"
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
  - "COleServerDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerDoc class"
  - "container/server applications"
  - "OLE containers, server documents"
  - "applications serveur OLE, managing server documents"
  - "OLE server documents"
  - "server documents, OLE"
  - "serveurs, OLE"
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleServerDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour les documents OLE serveur.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerDoc::COleServerDoc](../Topic/COleServerDoc::COleServerDoc.md)|Construit un objet `COleServerDoc`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerDoc::ActivateDocObject](../Topic/COleServerDoc::ActivateDocObject.md)|Lance le document associé de DocObject.|  
|[COleServerDoc::ActivateInPlace](../Topic/COleServerDoc::ActivateInPlace.md)|Lance le document pour la modification sur place.|  
|[COleServerDoc::DeactivateAndUndo](../Topic/COleServerDoc::DeactivateAndUndo.md)|Place l'interface utilisateur du serveur.|  
|[COleServerDoc::DiscardUndoState](../Topic/COleServerDoc::DiscardUndoState.md)|Ignore les informations d'état d'annulation.|  
|[COleServerDoc::GetClientSite](../Topic/COleServerDoc::GetClientSite.md)|Extrait un pointeur vers l'interface sous\-jacente d' `IOleClientSite` .|  
|[COleServerDoc::GetEmbeddedItem](../Topic/COleServerDoc::GetEmbeddedItem.md)|Retourne un pointeur vers un élément représentant le document entier.|  
|[COleServerDoc::GetItemClipRect](../Topic/COleServerDoc::GetItemClipRect.md)|Retourne le rectangle de découpage actuel pour la modification sur place.|  
|[COleServerDoc::GetItemPosition](../Topic/COleServerDoc::GetItemPosition.md)|Retourne le rectangle de position actuelle, par rapport à la zone cliente de l'application conteneur, pour la modification sur place.|  
|[COleServerDoc::GetZoomFactor](../Topic/COleServerDoc::GetZoomFactor.md)|Retourne le facteur de zoom en pixels.|  
|[COleServerDoc::IsDocObject](../Topic/COleServerDoc::IsDocObject.md)|Détermine si le document est DocObject.|  
|[COleServerDoc::IsEmbedded](../Topic/COleServerDoc::IsEmbedded.md)|Indique si le document est incorporé dans un document ou un conteneur qui autonome.|  
|[COleServerDoc::IsInPlaceActive](../Topic/COleServerDoc::IsInPlaceActive.md)|Retourne `TRUE` si l'élément est actuellement exécuté en place.|  
|[COleServerDoc::NotifyChanged](../Topic/COleServerDoc::NotifyChanged.md)|Prévient les conteneurs que l'utilisateur a modifié le document.|  
|[COleServerDoc::NotifyClosed](../Topic/COleServerDoc::NotifyClosed.md)|Prévient les conteneurs que l'utilisateur a fermé le document.|  
|[COleServerDoc::NotifyRename](../Topic/COleServerDoc::NotifyRename.md)|Prévient les conteneurs que l'utilisateur a renommé le document.|  
|[COleServerDoc::NotifySaved](../Topic/COleServerDoc::NotifySaved.md)|Prévient les conteneurs que l'utilisateur a enregistré le document.|  
|[COleServerDoc::OnDeactivate](../Topic/COleServerDoc::OnDeactivate.md)|Appelé par l'infrastructure lorsque l'utilisateur place un élément qui a été démarré en place.|  
|[COleServerDoc::OnDeactivateUI](../Topic/COleServerDoc::OnDeactivateUI.md)|Appelé par l'infrastructure pour détruire des contrôles et d'autres éléments d'interface utilisateur l'a créée pour l'activation sur place.|  
|[COleServerDoc::OnDocWindowActivate](../Topic/COleServerDoc::OnDocWindowActivate.md)|Appelé par l'infrastructure lorsque la fenêtre frame de document du conteneur est activée ou désactivée.|  
|[COleServerDoc::OnResizeBorder](../Topic/COleServerDoc::OnResizeBorder.md)|Appelé par l'infrastructure lorsque la fenêtre frame ou la fenêtre de document de l'application conteneur est redimensionnée.|  
|[COleServerDoc::OnShowControlBars](../Topic/COleServerDoc::OnShowControlBars.md)|Appelé par l'infrastructure pour afficher ou masquer des barres de contrôles pour la modification sur place.|  
|[COleServerDoc::OnUpdateDocument](../Topic/COleServerDoc::OnUpdateDocument.md)|Appelé par l'infrastructure lorsqu'un document serveur qui est un élément inclus est enregistré, la mise à jour la copie du conteneur de l'élément.|  
|[COleServerDoc::RequestPositionChange](../Topic/COleServerDoc::RequestPositionChange.md)|Modifie la position du frame de modification sur place.|  
|[COleServerDoc::SaveEmbedding](../Topic/COleServerDoc::SaveEmbedding.md)|Indique l'application conteneur d'enregistrer le document.|  
|[COleServerDoc::ScrollContainerBy](../Topic/COleServerDoc::ScrollContainerBy.md)|Fait défiler le document conteneur.|  
|[COleServerDoc::UpdateAllItems](../Topic/COleServerDoc::UpdateAllItems.md)|Prévient les conteneurs que l'utilisateur a modifié le document.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerDoc::CreateInPlaceFrame](../Topic/COleServerDoc::CreateInPlaceFrame.md)|Appelé par l'infrastructure pour créer une fenêtre frame pour la modification sur place.|  
|[COleServerDoc::DestroyInPlaceFrame](../Topic/COleServerDoc::DestroyInPlaceFrame.md)|Appelé par l'infrastructure pour détruire une fenêtre frame pour la modification sur place.|  
|[COleServerDoc::GetDocObjectServer](../Topic/COleServerDoc::GetDocObjectServer.md)|Remplacez cette fonction pour créer un nouvel objet d' `CDocObjectServer` et pour indiquer que ce document est un conteneur de DocObject.|  
|[COleServerDoc::OnClose](../Topic/COleServerDoc::OnClose.md)|Appelé par l'infrastructure lorsque demandes d'un conteneur de fermer le document.|  
|[COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md)|Exécute une commande spécifiée ou les affichages permettent de la commande.|  
|[COleServerDoc::OnFrameWindowActivate](../Topic/COleServerDoc::OnFrameWindowActivate.md)|Appelé par l'infrastructure lorsque la fenêtre frame du conteneur est activée ou désactivée.|  
|[COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md)|Appelé pour obtenir `COleServerItem` qui représente le document entier ; utilisé pour obtenir un élément inline.  Implémentation requise.|  
|[COleServerDoc::OnReactivateAndUndo](../Topic/COleServerDoc::OnReactivateAndUndo.md)|Appelé par l'infrastructure pour annuler les modifications apportées pendant la modification sur place.|  
|[COleServerDoc::OnSetHostNames](../Topic/COleServerDoc::OnSetHostNames.md)|Appelé par l'infrastructure lorsqu'un conteneur affecte le titre de la fenêtre pour un objet incorporé.|  
|[COleServerDoc::OnSetItemRects](../Topic/COleServerDoc::OnSetItemRects.md)|Appelé par l'infrastructure pour positionner la fenêtre frame de modification sur place dans la fenêtre de l'application conteneur.|  
|[COleServerDoc::OnShowDocument](../Topic/COleServerDoc::OnShowDocument.md)|Appelé par l'infrastructure pour afficher ou masquer le document.|  
  
## Notes  
 Un document serveur peut contenir des objets de [COleServerItem](../../mfc/reference/coleserveritem-class.md) , qui représentent l'interface de serveur à un incorporé ou des éléments liés.  Lorsqu'une application serveur est lancée par un conteneur de modifier un élément inline, l'élément est chargé comme son propre document serveur ; l'objet d' `COleServerDoc` contient un seul objet d' `COleServerItem` , comprenant le document entier.  Lorsqu'une application serveur est lancée par un conteneur de modifier un élément lié, un document existant est chargé à partir de le disque ; une partie du contenu du document est mise en surbrillance pour indiquer l'élément lié.  
  
 Les objets d'`COleServerDoc` peuvent également contenir des éléments de la classe de [COleClientItem](../../mfc/reference/coleclientitem-class.md) .  Cela vous permet de créer des applications aux conteneurs de serveur.  L'infrastructure fournit des fonctions pour signaler correctement les éléments d' `COleClientItem` en entretenant `COleServerItem` objets.  
  
 Si votre application serveur ne fait pas en charge, un document serveur contient toujours un seul élément du serveur, qui représente l'objet incorporé entier comme un document.  Si votre application serveur fait en charge, elle doit créer un élément du serveur chaque fois qu'une sélection est copié dans le presse\-papiers.  
  
 Pour utiliser `COleServerDoc`, dérivez une classe de celle\-ci et implémentez la fonction membre d' [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) , qui permet à votre serveur aux éléments inclus par prise en charge.  Dérivez une classe d' `COleServerItem` pour implémenter des éléments dans vos documents, et retournez les objets de cette classe d' `OnGetEmbeddedItem`.  
  
 Pour prendre en charge des éléments liés, `COleServerDoc` fournit la fonction membre d' [OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md) .  Vous pouvez utiliser l'implémentation par défaut ou la substituer si vous avez votre propre façon de gérer les éléments du document.  
  
 Vous avez besoin d'un `COleServerDoc`classe dérivée pour chaque type de document serveur prise en charge par votre application.  Par exemple, si votre application serveur prend en charge les feuilles de calcul et des graphiques, vous avez besoin de deux `COleServerDoc`\- classes dérivées.  
  
 Pour plus d'informations sur les serveurs, consultez l'article [serveurs : implémenter un serveur](../../mfc/servers-implementing-a-server.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)