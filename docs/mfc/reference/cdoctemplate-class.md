---
title: "CDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocTemplate class"
  - "modèles de document"
  - "modèles, document"
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe de base abstraite qui définit les fonctionnalités de base des modèles de document.  
  
## Syntaxe  
  
```  
class CDocTemplate : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocTemplate::CDocTemplate](../Topic/CDocTemplate::CDocTemplate.md)|Construit un objet `CDocTemplate`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocTemplate::AddDocument](../Topic/CDocTemplate::AddDocument.md)|Ajoute un document à un modèle.|  
|[CDocTemplate::CloseAllDocuments](../Topic/CDocTemplate::CloseAllDocuments.md)|Ferme tous les documents associés à ce modèle.|  
|[CDocTemplate::CreateNewDocument](../Topic/CDocTemplate::CreateNewDocument.md)|Crée un document.|  
|[CDocTemplate::CreateNewFrame](../Topic/CDocTemplate::CreateNewFrame.md)|Crée une nouvelle fenêtre frame contenant un document et une vue.|  
|[CDocTemplate::CreateOleFrame](../Topic/CDocTemplate::CreateOleFrame.md)|Crée une fenêtre frame OLE\-activée.|  
|[CDocTemplate::CreatePreviewFrame](../Topic/CDocTemplate::CreatePreviewFrame.md)|Crée un frame enfant utilisé pour l'aperçu riche.|  
|[CDocTemplate::GetDocString](../Topic/CDocTemplate::GetDocString.md)|Extrait une chaîne associée au type de document.|  
|[CDocTemplate::GetFirstDocPosition](../Topic/CDocTemplate::GetFirstDocPosition.md)|Extrait la position du premier document associé à ce modèle.|  
|[CDocTemplate::GetNextDoc](../Topic/CDocTemplate::GetNextDoc.md)|Récupère un document et la position de la suivante.|  
|[CDocTemplate::InitialUpdateFrame](../Topic/CDocTemplate::InitialUpdateFrame.md)|Initialise la fenêtre frame, et la rend éventuellement visible.|  
|[CDocTemplate::LoadTemplate](../Topic/CDocTemplate::LoadTemplate.md)|Charge les ressources pour `CDocTemplate` donné ou une classe dérivée.|  
|[CDocTemplate::MatchDocType](../Topic/CDocTemplate::MatchDocType.md)|Détermine le niveau de confiance en correspondance entre un type de document et ce modèle.|  
|[CDocTemplate::OpenDocumentFile](../Topic/CDocTemplate::OpenDocumentFile.md)|Ouvre un fichier spécifié par un nom de chemin d'accès.|  
|[CDocTemplate::RemoveDocument](../Topic/CDocTemplate::RemoveDocument.md)|Supprime un document à partir d'un modèle.|  
|[CDocTemplate::SaveAllModified](../Topic/CDocTemplate::SaveAllModified.md)|Enregistre les documents associés à ce modèle qui ont été modifiés.|  
|[CDocTemplate::SetContainerInfo](../Topic/CDocTemplate::SetContainerInfo.md)|Détermine les ressources pour les conteneurs OLE en modifiant un élément OLE sur place.|  
|[CDocTemplate::SetDefaultTitle](../Topic/CDocTemplate::SetDefaultTitle.md)|Affiche le titre par défaut dans la barre de titre de la fenêtre de document.|  
|[CDocTemplate::SetPreviewInfo](../Topic/CDocTemplate::SetPreviewInfo.md)|Installations hors de gestionnaire de processus d'aperçu.|  
|[CDocTemplate::SetServerInfo](../Topic/CDocTemplate::SetServerInfo.md)|Détermine les ressources et les classes lorsque le document serveur est inclus ou sur place modifié.|  
  
## Notes  
 Vous créez généralement un ou plusieurs modèles de document dans l'implémentation de la fonction d' `InitInstance` de votre application.  Un modèle de document définit les relations entre trois types de classes :  
  
-   Une classe de document, que vous dérivez de **CDocument**.  
  
-   Une classe d'affichage, qui affiche des données provenant de la classe de document listé en haut.  Vous pouvez dériver cette classe d' `CView`, d' `CScrollView`, d' `CFormView`, ou d' `CEditView`.  \(Vous pouvez également utiliser `CEditView` directement.\)  
  
-   Une classe de fenêtre frame, qui contient la vue.  Pour une application de \(SDI\) d'interface monodocument \(SDI, vous dérivez la classe d' `CFrameWnd`.  Pour une application d'interface multidocument \(MDI\), vous dérivez la classe d' `CMDIChildWnd`.  Si vous n'avez pas besoin de personnaliser le comportement de la fenêtre frame, vous pouvez utiliser `CFrameWnd` ou `CMDIChildWnd` directement sans dériver votre propre classe.  
  
 Votre application possède un modèle de document pour chaque type de document prise en charge.  Par exemple, si vos documents et feuilles texte de l'application prend en charge, l'application a deux objets de modèle de document.  Chaque modèle de document est chargé de créer et de gérer tous les documents de son type.  
  
 Le modèle de document stocke les pointeurs vers des objets d' `CRuntimeClass` pour le document, la vue, et les classes de fenêtre frame.  Ces objets d' `CRuntimeClass` sont spécifiés en construisant un modèle de document.  
  
 Le modèle de document contient l'ID les ressources utilisées par le type de document \(tel que le menu, l'icône, ou les ressources table d'accélérateurs\).  Le modèle de document a également des chaînes contenant des informations supplémentaires sur son type de document.  Celles\-ci incluent le nom du type de document \(par exemple, « feuille de calcul »\) et de l'extension de fichier \(par exemple, « .xls »\).  Éventuellement, il peut contenir d'autres chaînes utilisées par l'interface utilisateur de l'application, la prise en charge du gestionnaire de fichiers windows, et de liaison et incorporation d'objets OLE \(\).  
  
 Si votre application est un conteneur OLE et\/ou un serveur, le modèle de document définit également l'ID du menu utilisé pendant l'activation sur place.  Si votre application est un OLE serveur, le modèle de document définit l'ID de la barre d'outils et du menu utilisés lors de l'activation sur place.  Vous spécifiez ces ressources OLE supplémentaires en appelant `SetContainerInfo` et `SetServerInfo`.  
  
 Étant donné qu' `CDocTemplate` est une classe abstraite, vous ne pouvez pas utiliser la classe directement.  Une application classique utilise un des deux `CDocTemplate`\- classes dérivées fournies par la bibliothèque MFC : `CSingleDocTemplate`, une interface SDI qui implémente, et `CMultiDocTemplate`, qui implémente MDI.  Consultez ces classes pour plus d'informations sur l'utilisation des modèles de document.  
  
 Si votre application requiert un paradigme d'interface utilisateur qui est fondamentalement différente SDI ou MDI, vous pouvez dériver votre propre classe d' `CDocTemplate`.  
  
 Pour plus d'informations sur `CDocTemplate`, consultez [Modèles de document et le processus de création du document\/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocTemplate`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CMultiDocTemplate Class](../../mfc/reference/cmultidoctemplate-class.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CEditView Class](../../mfc/reference/ceditview-class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CFrameWnd Class](../../mfc/reference/cframewnd-class.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)