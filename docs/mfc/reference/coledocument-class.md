---
title: "COleDocument Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocument class"
  - "documents, OLE"
  - "OLE containers, client items"
  - "OLE documents"
  - "OLE documents, classe de base"
  - "visual editing, OLE document base class"
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe de base pour les documents OLE qui prennent en charge la modification sur place.  
  
## Syntaxe  
  
```  
class COleDocument : public CDocument  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDocument::COleDocument](../Topic/COleDocument::COleDocument.md)|Construit un objet `COleDocument`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDocument::AddItem](../Topic/COleDocument::AddItem.md)|Ajoute un élément à la liste d'éléments mis à jour par le document.|  
|[COleDocument::ApplyPrintDevice](../Topic/COleDocument::ApplyPrintDevice.md)|Définit le périphérique de copie\- cible pour tous les éléments clients dans le document.|  
|[COleDocument::EnableCompoundFile](../Topic/COleDocument::EnableCompoundFile.md)|Documents de provoque un enregistrement à l'aide de le OLE format de fichier structurée de mémoire.|  
|[COleDocument::GetInPlaceActiveItem](../Topic/COleDocument::GetInPlaceActiveItem.md)|Retourne l'élément OLE actuellement actif sur place.|  
|[COleDocument::GetNextClientItem](../Topic/COleDocument::GetNextClientItem.md)|Obtient l'élément client pour itérer.|  
|[COleDocument::GetNextItem](../Topic/COleDocument::GetNextItem.md)|Obtient l'élément suivant de le document pour itérer.|  
|[COleDocument::GetNextServerItem](../Topic/COleDocument::GetNextServerItem.md)|Obtient l'élément suivant du serveur pour itérer.|  
|[COleDocument::GetPrimarySelectedItem](../Topic/COleDocument::GetPrimarySelectedItem.md)|Retourne l'élément OLE sélectionné primaire dans le document.|  
|[COleDocument::GetStartPosition](../Topic/COleDocument::GetStartPosition.md)|Obtient la position d'origine pour démarrer l'itération.|  
|[COleDocument::HasBlankItems](../Topic/COleDocument::HasBlankItems.md)|Contrôles pour les éléments vides dans le document.|  
|[COleDocument::OnShowViews](../Topic/COleDocument::OnShowViews.md)|Appelé lorsque le document est visible ou invisible.|  
|[COleDocument::RemoveItem](../Topic/COleDocument::RemoveItem.md)|Supprime un élément de la liste d'éléments mis à jour par le document.|  
|[COleDocument::UpdateModifiedFlag](../Topic/COleDocument::UpdateModifiedFlag.md)|Marque le document comme modifié si de OLE éléments contenus l'un des ont été modifiés.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDocument::OnEditChangeIcon](../Topic/COleDocument::OnEditChangeIcon.md)|Gère des événements dans la commande de menu d'icône de modification.|  
|[COleDocument::OnEditConvert](../Topic/COleDocument::OnEditConvert.md)|Gère la conversion d'un incorporé ou d'un objet dépendant d'un type en un autre.|  
|[COleDocument::OnEditLinks](../Topic/COleDocument::OnEditLinks.md)|Gère des événements dans des liens commande identities dans le menu Edition.|  
|[COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)|Envoie un message électronique avec le document lié.|  
|[COleDocument::OnUpdateEditChangeIcon](../Topic/COleDocument::OnUpdateEditChangeIcon.md)|Appelé par l'infrastructure pour mettre à jour la commande interface utilisateur pour l'option du menu de l'icône de modification\/modification.|  
|[COleDocument::OnUpdateEditLinksMenu](../Topic/COleDocument::OnUpdateEditLinksMenu.md)|Appelé par l'infrastructure pour mettre à jour la commande interface utilisateur pour l'option du menu de modification\/liens.|  
|[COleDocument::OnUpdateObjectVerbMenu](../Topic/COleDocument::OnUpdateObjectVerbMenu.md)|Appelé par l'infrastructure pour mettre à jour la commande interface utilisateur pour l'option du menu de modification\/*Nomobjet* et le sous\-menu de verbe a accédé de la modification\/*Nomobjet*.|  
|[COleDocument::OnUpdatePasteLinkMenu](../Topic/COleDocument::OnUpdatePasteLinkMenu.md)|Appelé par l'infrastructure pour mettre à jour la commande interface utilisateur pour l'option du menu de spécial de collage.|  
|[COleDocument::OnUpdatePasteMenu](../Topic/COleDocument::OnUpdatePasteMenu.md)|Appelé par l'infrastructure pour mettre à jour la commande interface utilisateur pour l'option du menu de collage.|  
  
## Notes  
 `COleDocument` est dérivé de **CDocument**, qui permet vos applications OLE d'utiliser l'architecture Document\/Vue fournie par la bibliothèque MFC.  
  
 `COleDocument` traite un document comme une collection d'objets de [CDocItem](../../mfc/reference/cdocitem-class.md) pour gérer de OLE éléments.  Le conteneur et les applications serveur requièrent une telle architecture parce que leurs documents doivent pouvoir contenir de OLE éléments.  Les classes de [COleServerItem](../../mfc/reference/coleserveritem-class.md) et de [COleClientItem](../../mfc/reference/coleclientitem-class.md) , les deux dérivées d' `CDocItem`, gèrent les interactions entre les applications et les éléments OLE.  
  
 Si vous écrivez une application conteneur simple, dérivez votre classe de document d' `COleDocument`.  Si vous écrivez une application conteneur qui prend en charge la liaison aux éléments inclus contenus par ses documents, dérivez votre classe de document de [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md).  Si vous écrivez un conteneur d'application serveur ou de la combinaison\/serveur, dérivez votre classe de document de [COleServerDoc](../../mfc/reference/coleserverdoc-class.md).  `COleLinkingDoc` et `COleServerDoc` sont dérivés d' `COleDocument`par conséquent, ces classes héritent tous les services disponibles dans `COleDocument` et **CDocument**.  
  
 Pour utiliser `COleDocument`, dérivez une classe de celle\-ci et ajoutez les fonctionnalités pour gérer les données non OLE de l'application ainsi qu'un incorporé ou des éléments liés.  Si vous définissez `CDocItem`\- classes dérivées pour stocker les données natives de l'application, vous pouvez utiliser l'implémentation par défaut définie par `COleDocument` pour stocker les données et OLE non OLE.  Vous pouvez également concevoir vos propres structures de données pour stocker les données non OLE séparément des éléments OLE.  Pour plus d'informations, consultez l'article. [conteneurs : fichiers composés](../../mfc/containers-compound-files.md).  
  
 **CDocument** prend envoyer votre document par le biais de la messagerie si la prise en charge de message MAPI \(\) est présent.  `COleDocument` a mis à jour [OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md) pour traiter des documents composés correctement.  Pour plus d'informations, consultez les articles [MAPI](../../mfc/mapi.md) et [Prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [CONTAINER d'exemple MFC](../../top/visual-cpp-samples.md)   
 [MFC exemple MFCBIND](../../top/visual-cpp-samples.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)