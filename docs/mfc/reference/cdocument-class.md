---
title: "CDocument Class | Microsoft Docs"
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
  - "CDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDocument class"
  - "gestion des commandes, documents and"
  - "routage des commandes, documents and"
  - "documents (C++), routage des commandes"
  - "documents (C++), document classes"
  - "documents (C++), vues multiples"
  - "documents (C++), sérialisation"
  - "fichiers (C++), documents"
  - "sérialisation (C++), documents and"
  - "vues (C++), document"
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités de base des classes définies par l'utilisateur de document.  
  
## Syntaxe  
  
```  
class CDocument : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocument::CDocument](../Topic/CDocument::CDocument.md)|Construit un objet `CDocument`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocument::AddView](../Topic/CDocument::AddView.md)|Joint une vue au document.|  
|[CDocument::BeginReadChunks](../Topic/CDocument::BeginReadChunks.md)|Initialise la lecture du segment.|  
|[CDocument::CanCloseFrame](../Topic/CDocument::CanCloseFrame.md)|Substituable avancées ; appelé avant de fermer une fenêtre frame consultant ce document.|  
|[CDocument::ClearChunkList](../Topic/CDocument::ClearChunkList.md)|Efface la liste de segment.|  
|[CDocument::ClearPathName](../Topic/CDocument::ClearPathName.md)|Efface le chemin d'accès de l'objet.|  
|[CDocument::DeleteContents](../Topic/CDocument::DeleteContents.md)|Appelé pour effectuer un nettoyage du document.|  
|[CDocument::FindChunk](../Topic/CDocument::FindChunk.md)|Recherche un segment avec un GUID spécifié.|  
|[CDocument::GetAdapter](../Topic/CDocument::GetAdapter.md)|Retourne un pointeur pour un objet implémentant l'interface d' `IDocument` .|  
|[CDocument::GetDocTemplate](../Topic/CDocument::GetDocTemplate.md)|Retourne un pointeur vers le modèle de document qui décrit le type du document.|  
|[CDocument::GetFile](../Topic/CDocument::GetFile.md)|Retourne un pointeur vers l'objet souhaité dans `CFile` .|  
|[CDocument::GetFirstViewPosition](../Topic/CDocument::GetFirstViewPosition.md)|Retourne la position de la première dans la liste des vues ; utilisé pour lancer l'itération.|  
|[CDocument::GetNextView](../Topic/CDocument::GetNextView.md)|Itère au sein de la liste de vues associées au document.|  
|[CDocument::GetPathName](../Topic/CDocument::GetPathName.md)|Retourne le chemin d'accès du fichier de données du document.|  
|[CDocument::GetThumbnail](../Topic/CDocument::GetThumbnail.md)|Appelé pour créer une bitmap à utiliser par le fournisseur miniature pour afficher l'aperçu.|  
|[CDocument::GetTitle](../Topic/CDocument::GetTitle.md)|Retourne le titre du document.|  
|[CDocument::InitializeSearchContent](../Topic/CDocument::InitializeSearchContent.md)|Appelé pour initialiser le contenu de recherche pour le gestionnaire de recherche.|  
|[CDocument::IsModified](../Topic/CDocument::IsModified.md)|Indique si le document a été modifié depuis lequel il a été en dernier enregistrement.|  
|[CDocument::IsSearchAndOrganizeHandler](../Topic/CDocument::IsSearchAndOrganizeHandler.md)|Indique si cette instance d'objet d' `CDocument` a été créée pour la recherche et organise le gestionnaire.|  
|[CDocument::LoadDocumentFromStream](../Topic/CDocument::LoadDocumentFromStream.md)|Appelé aux données de document de chargement du flux.|  
|[CDocument::OnBeforeRichPreviewFontChanged](../Topic/CDocument::OnBeforeRichPreviewFontChanged.md)|Appelé avant la police d'aperçu riche est modifié.|  
|[CDocument::OnChangedViewList](../Topic/CDocument::OnChangedViewList.md)|Appelé après une vue soit ajoutée ou supprimée du document.|  
|[CDocument::OnCloseDocument](../Topic/CDocument::OnCloseDocument.md)|Appelé pour fermer le document.|  
|[CDocument::OnCreatePreviewFrame](../Topic/CDocument::OnCreatePreviewFrame.md)|Appelé par l'infrastructure lorsqu'il doit créer un frame d'aperçu de l'aperçu riche.|  
|[CDocument::OnDocumentEvent](../Topic/CDocument::OnDocumentEvent.md)|Appelé par l'infrastructure en réponse à un événement de document.|  
|[CDocument::OnDrawThumbnail](../Topic/CDocument::OnDrawThumbnail.md)|Substituez cette méthode dans une classe dérivée pour dessiner le contenu de l'aperçu.|  
|[CDocument::OnLoadDocumentFromStream](../Topic/CDocument::OnLoadDocumentFromStream.md)|Appelé par l'infrastructure lorsqu'il doit charger des données de document du flux.|  
|[CDocument::OnNewDocument](../Topic/CDocument::OnNewDocument.md)|Appelé pour créer un document.|  
|[CDocument::OnOpenDocument](../Topic/CDocument::OnOpenDocument.md)|Appelé pour ouvrir un document existant.|  
|[CDocument::OnPreviewHandlerQueryFocus](../Topic/CDocument::OnPreviewHandlerQueryFocus.md)|Dirige le gestionnaire d'aperçu pour retourner le HWND d'appeler la fonction de GetFocus.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](../Topic/CDocument::OnPreviewHandlerTranslateAccelerator.md)|Dirige le gestionnaire d'aperçu pour gérer une séquence de touches passée de la pompe de messages du processus dans lequel le gestionnaire d'aperçu exécute.|  
|[CDocument::OnRichPreviewBackColorChanged](../Topic/CDocument::OnRichPreviewBackColorChanged.md)|Appelé lorsque la couleur d'arrière\-plan d'aperçu de riches a changé.|  
|[CDocument::OnRichPreviewFontChanged](../Topic/CDocument::OnRichPreviewFontChanged.md)|Appelé lorsque la police d'aperçu de riches a changé.|  
|[CDocument::OnRichPreviewSiteChanged](../Topic/CDocument::OnRichPreviewSiteChanged.md)|Appelé lorsque le site d'aperçu de riches a changé.|  
|[CDocument::OnRichPreviewTextColorChanged](../Topic/CDocument::OnRichPreviewTextColorChanged.md)|Appelé lorsque la couleur du texte d'aperçu de riches a changé.|  
|[CDocument::OnSaveDocument](../Topic/CDocument::OnSaveDocument.md)|Appelé pour enregistrer le document sur le disque.|  
|[CDocument::OnUnloadHandler](../Topic/CDocument::OnUnloadHandler.md)|Appelé par l'infrastructure lorsque le gestionnaire d'aperçu est déchargé.|  
|[CDocument::PreCloseFrame](../Topic/CDocument::PreCloseFrame.md)|Appelé avant la fenêtre frame est fermé.|  
|[CDocument::ReadNextChunkValue](../Topic/CDocument::ReadNextChunkValue.md)|La valeur de segment de lectures.|  
|[CDocument::ReleaseFile](../Topic/CDocument::ReleaseFile.md)|Libère un fichier pour le rendre disponible pour une utilisation par d'autres applications.|  
|[CDocument::RemoveChunk](../Topic/CDocument::RemoveChunk.md)|Supprime un segment avec un GUID spécifié.|  
|[CDocument::RemoveView](../Topic/CDocument::RemoveView.md)|Détache une vue du document.|  
|[CDocument::ReportSaveLoadException](../Topic/CDocument::ReportSaveLoadException.md)|Substituable avancées ; appelé lorsqu'une opération ouvert ou d'enregistrement ne peut pas être effectuée en raison d'une exception.|  
|[CDocument::SaveModified](../Topic/CDocument::SaveModified.md)|Substituable avancées ; appelé pour indiquer à l'utilisateur si le document doit être enregistré.|  
|[CDocument::SetChunkValue](../Topic/CDocument::SetChunkValue.md)|Définit une valeur de segment.|  
|[CDocument::SetModifiedFlag](../Topic/CDocument::SetModifiedFlag.md)|Place une balise qui indique que vous avez modifié le document depuis lequel il a été en dernier enregistrement.|  
|[CDocument::SetPathName](../Topic/CDocument::SetPathName.md)|Définit le chemin d'accès du fichier de données utilisé par le document.|  
|[CDocument::SetTitle](../Topic/CDocument::SetTitle.md)|Définit le titre du document.|  
|[CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)|Signale toutes les vues que le document a été modifiées.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocument::OnFileSendMail](../Topic/CDocument::OnFileSendMail.md)|Envoie un message électronique avec le document lié.|  
|[CDocument::OnUpdateFileSendMail](../Topic/CDocument::OnUpdateFileSendMail.md)|Active la commande de messagerie d'envoyer si la prise en charge de messagerie est présent.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDocument::m\_bGetThumbnailMode](../Topic/CDocument::m_bGetThumbnailMode.md)|Spécifie que l'objet d' `CDocument` a été créé par le dllhost des aperçus.  Doit être signé `CView::OnDraw`.|  
|[CDocument::m\_bPreviewHandlerMode](../Topic/CDocument::m_bPreviewHandlerMode.md)|Spécifie que l'objet d' `CDocument` a été créé par le prevhost pour `Rich Preview`.  Doit être signé `CView::OnDraw`.|  
|[CDocument::m\_bSearchMode](../Topic/CDocument::m_bSearchMode.md)|Spécifie que l'objet d' `CDocument` a été créé par l'indexeur ou autre application de recherche.|  
|[CDocument::m\_clrRichPreviewBackColor](../Topic/CDocument::m_clrRichPreviewBackColor.md)|Spécifie la couleur d'arrière\-plan de la fenêtre d'aperçu riche.  Cette couleur est définie par l'hôte.|  
|[CDocument::m\_clrRichPreviewTextColor](../Topic/CDocument::m_clrRichPreviewTextColor.md)|Spécifie la couleur de premier plan de la fenêtre d'aperçu riche.  Cette couleur est définie par l'hôte.|  
|[CDocument::m\_lfRichPreviewFont](../Topic/CDocument::m_lfRichPreviewFont.md)|Spécifie la police du texte de la fenêtre d'aperçu riche.  Ces informations de police sont définies par l'hôte.|  
  
## Notes  
 Un document représente l'unité de données que l'utilisateur en général ouvre avec la commande ouverte de fichier et enregistre avec la commande de sauvegarde de fichier.  
  
 **CDocument** prend en charge les opérations standard telles que la création d'un document, le chargement, et l'enregistrer.  L'infrastructure manipule des documents à l'aide de l'interface définie par **CDocument**.  
  
 Une application peut prendre en charge plusieurs types de document ; par exemple, une application peut prendre en charge des feuilles et des documents texte.  Chaque type de document a un modèle de document associé ; le modèle de document spécifie les ressources \(par exemple, menu, icône, ou table d'accélérateurs\) sont utilisés pour ce type de document.  Chaque document contient un pointeur vers l'objet associé à `CDocTemplate` .  
  
 Les utilisateurs interagissent avec un document par les objets de [CView](../../mfc/reference/cview-class.md) associés à celui\-ci.  Une vue affiche une image du document dans une fenêtre frame et interprète les entrées d'utilisateur comme opérations sur le document.  Un document peut avoir plusieurs affichages associés à celui\-ci.  Lorsque l'utilisateur ouvre une fenêtre sur un document, l'infrastructure crée une vue et la lié au document.  Le modèle de document spécifie le type de vue et de fenêtre frame sont utilisées pour afficher chaque type de document.  
  
 Les documents font partie du routage des commandes standard de l'infrastructure et reçoivent par conséquent des commandes des composants standard d'interface utilisateur \(tels que l'élément de menu de sauvegarde de fichier\).  Un document reçoit des commandes faites suivre par la vue active.  Si le document ne gère pas la commande donnée, il effectue le suivi de la commande le modèle de document qui gère la.  
  
 Lorsque les données d'un document sont modifiées, chacune de ses vues doivent refléter ces modifications.  **CDocument** fournit la fonction membre d' [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) pour que vous informiez les vues de ces modifications, les vues peuvent se repeindre si nécessaire.  L'infrastructure invite l'utilisateur à enregistrer un fichier modifié avant de le fermer.  
  
 Pour implémenter des documents dans une application type, vous devez effectuer les opérations suivantes :  
  
-   Dérivez une classe de **CDocument** pour chaque type de document.  
  
-   Ajoutez des variables membres pour stocker les données de chaque document.  
  
-   Implémentez les fonctions membres pour lire et modifier les données du document.  Les vues du document sont les utilisateurs les plus importants de ces fonctions membres.  
  
-   Substituez la fonction membre de [CObject::Serialize](../Topic/CObject::Serialize.md) dans votre classe de document pour écrire et lire les données du document vers le disque.  
  
 **CDocument** prend envoyer votre document par le biais de la messagerie si la prise en charge de message MAPI \(\) est présent.  Consultez les articles [MAPI](../../mfc/mapi.md) et [Prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Pour plus d'informations sur **CDocument**, consultez [sérialisation](../../mfc/serialization-in-mfc.md), [Rubriques d'architecture Document\/Vue](../../mfc/document-view-architecture.md), et le [création de document\/vue](../../mfc/document-view-creation.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [MFC exemple MDIDOCVW](../../top/visual-cpp-samples.md)   
 [MFC exemple SNAPVW](../../top/visual-cpp-samples.md)   
 [CN d'exemple MFC](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)