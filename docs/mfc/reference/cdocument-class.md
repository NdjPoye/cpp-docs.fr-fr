---
title: CDocument (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocument
dev_langs:
- C++
helpviewer_keywords:
- documents [C++], serialization
- files [C++], documents
- command handling, documents and
- documents [C++], document classes
- documents [C++], multiple views
- serialization [C++], documents and
- CDocument class
- command routing, documents and
- views [C++], document
- documents [C++], command routing
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4d64b95f77139d984b855e710f3951434e489dd5
ms.lasthandoff: 02/24/2017

---
# <a name="cdocument-class"></a>CDocument (classe)
Fournit les fonctionnalités de base pour les classes de documents définies par l'utilisateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDocument : public CCmdTarget  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocument::CDocument](#cdocument)|Construit un objet `CDocument`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocument::AddView](#addview)|Joint une vue au document.|  
|[CDocument::BeginReadChunks](#beginreadchunks)|Initialise segment lecture.|  
|[CDocument::CanCloseFrame](#cancloseframe)|Advanced substituable ; appelé avant la fermeture d’une fenêtre frame afficher ce document.|  
|[CDocument::ClearChunkList](#clearchunklist)|Efface la liste segment.|  
|[CDocument::ClearPathName](#clearpathname)|Efface le chemin d’accès de l’objet document.|  
|[CDocument::DeleteContents](#deletecontents)|Appelée pour effectuer un nettoyage du document.|  
|[CDocument::FindChunk](#findchunk)|Recherche d’un segment avec le GUID spécifié.|  
|[CDocument::GetAdapter](#getadapter)|Retourne un pointeur vers l’objet qui implémente `IDocument` interface.|  
|[CDocument::GetDocTemplate](#getdoctemplate)|Retourne un pointeur vers le modèle de document qui décrit le type du document.|  
|[CDocument::GetFile](#getfile)|Retourne un pointeur vers l’élément `CFile` objet.|  
|[CDocument::GetFirstViewPosition](#getfirstviewposition)|Retourne la position de la première dans la liste des vues ; utilisé pour lancer l’itération.|  
|[CDocument::GetNextView](#getnextview)|Parcourt la liste de vues associée au document.|  
|[CDocument::GetPathName](#getpathname)|Retourne le chemin d’accès du fichier de données du document.|  
|[CDocument::GetThumbnail](#getthumbnail)|Appelée pour créer une image bitmap à être utilisé par le fournisseur de miniatures pour afficher la miniature.|  
|[CDocument::GetTitle](#gettitle)|Retourne le titre du document.|  
|[CDocument::InitializeSearchContent](#initializesearchcontent)|Appelée pour initialiser le contenu de recherche pour le Gestionnaire de recherche.|  
|[CDocument::IsModified](#ismodified)|Indique si le document a été modifié depuis son dernier enregistrement.|  
|[CDocument::IsSearchAndOrganizeHandler](#issearchandorganizehandler)|Indique si cette instance de `CDocument` objet a été créé pour le Gestionnaire de recherche s’organiser.|  
|[CDocument::LoadDocumentFromStream](#loaddocumentfromstream)|Appelée pour charger les données de document de flux de données.|  
|[CDocument::OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|Appelé avant la modification de la police de l’aperçu détaillé.|  
|[CDocument::OnChangedViewList](#onchangedviewlist)|Appelé après qu’une vue est ajoutée ou supprimée du document.|  
|[CDocument::OnCloseDocument](#onclosedocument)|Appelée pour fermer le document.|  
|[CDocument::OnCreatePreviewFrame](#oncreatepreviewframe)|Appelé par l’infrastructure lorsqu’il a besoin créer une image d’aperçu pour l’aperçu riche.|  
|[CDocument::OnDocumentEvent](#ondocumentevent)|Appelé par l’infrastructure en réponse à un événement de document.|  
|[CDocument::OnDrawThumbnail](#ondrawthumbnail)|Substituez cette méthode dans une classe dérivée pour dessiner le contenu de la miniature.|  
|[CDocument::OnLoadDocumentFromStream](#onloaddocumentfromstream)|Appelé par l’infrastructure lorsqu’il a besoin charger les données de document de flux de données.|  
|[CDocument::OnNewDocument](#onnewdocument)|Appelée pour créer un nouveau document.|  
|[CDocument::OnOpenDocument](#onopendocument)|Appelé pour ouvrir un document existant.|  
|[CDocument::OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|Dirige le Gestionnaire d’aperçus pour retourner le HWND de l’appel de la fonction GetFocus.|  
|[CDocument::OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|Dirige le Gestionnaire d’aperçus pour gérer une séquence de touches transmis par la pompe de messages du processus dans lequel s’exécute le Gestionnaire d’aperçus.|  
|[CDocument::OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|Appelé lorsque la couleur d’arrière-plan aperçu détaillé a changé.|  
|[CDocument::OnRichPreviewFontChanged](#onrichpreviewfontchanged)|Appelé lorsque l’aperçu riche police a été modifiée.|  
|[CDocument::OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|Appelé lorsque le site d’aperçu détaillé a changé.|  
|[CDocument::OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|Appelé lorsque la couleur du texte enrichi Aperçu a changé.|  
|[CDocument::OnSaveDocument](#onsavedocument)|Appelée pour enregistrer le document sur le disque.|  
|[CDocument::OnUnloadHandler](#onunloadhandler)|Appelé par l’infrastructure lorsque le Gestionnaire d’aperçus est en cours de déchargement.|  
|[CDocument::PreCloseFrame](#precloseframe)|Appelé avant la fermeture de la fenêtre frame.|  
|[CDocument::ReadNextChunkValue](#readnextchunkvalue)|Lit la valeur suivante de segment.|  
|[CDocument::ReleaseFile](#releasefile)|Libère un fichier pour le rendre disponible pour une utilisation par d’autres applications.|  
|[CDocument::RemoveChunk](#removechunk)|Supprime un segment avec le GUID spécifié.|  
|[CDocument::RemoveView](#removeview)|Détache une vue à partir du document.|  
|[CDocument::ReportSaveLoadException](#reportsaveloadexception)|Advanced substituable ; appelé lorsqu’une est ouverte ou l’opération de sauvegarde ne peut pas être effectuée en raison d’une exception.|  
|[CDocument::SaveModified](#savemodified)|Advanced substituable ; appelée pour demander à l’utilisateur si le document doit être enregistré.|  
|[CDocument::SetChunkValue](#setchunkvalue)|Définit une valeur de segment.|  
|[CDocument::SetModifiedFlag](#setmodifiedflag)|Définit un indicateur qui signale que vous avez modifié le document depuis son dernier enregistrement.|  
|[CDocument::SetPathName](#setpathname)|Définit le chemin d’accès du fichier de données utilisé par le document.|  
|[CDocument::SetTitle](#settitle)|Définit le titre du document.|  
|[CDocument::UpdateAllViews](#updateallviews)|Informe toutes les vues de document a été modifié.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocument::OnFileSendMail](#onfilesendmail)|Envoie un message électronique avec le document joint.|  
|[CDocument::OnUpdateFileSendMail](#onupdatefilesendmail)|Active la commande Envoyer un message si la prise en charge de la messagerie est présent.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocument::m_bGetThumbnailMode](#m_bgetthumbnailmode)|Spécifie que `CDocument` objet a été créé par dllhost pour les miniatures. Doivent être archivés `CView::OnDraw`.|  
|[CDocument::m_bPreviewHandlerMode](#m_bpreviewhandlermode)|Spécifie que `CDocument` objet a été créé par prevhost pour `Rich Preview`. Doivent être archivés `CView::OnDraw`.|  
|[CDocument::m_bSearchMode](#m_bsearchmode)|Spécifie que `CDocument` objet a été créé par un indexeur ou une autre application de recherche.|  
|[CDocument::m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|Spécifie la couleur d’arrière-plan de la fenêtre d’aperçu détaillé. Cette couleur est définie par l’hôte.|  
|[CDocument::m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|Spécifie la couleur de premier plan de la fenêtre d’aperçu détaillé. Cette couleur est définie par l’hôte.|  
|[CDocument::m_lfRichPreviewFont](#m_lfrichpreviewfont)|Spécifie la police du texte de la fenêtre d’aperçu détaillé. Ces informations de police sont définies par l’hôte.|  
  
## <a name="remarks"></a>Remarques  
 Un document représente l’unité de données que l’utilisateur généralement s’ouvre avec la commande Ouvrir un fichier et l’enregistre avec la commande Enregistrer.  
  
 **CDocument** prend en charge les opérations standards telles que la création d’un document, son chargement et l’enregistrer. Manipule les documents à l’aide de l’interface définie par l’infrastructure **CDocument**.  
  
 Une application peut prendre en charge plusieurs types de document. par exemple, une application peut prendre en charge des feuilles de calcul et des documents de texte. Chaque type de document a un modèle de document associé ; le modèle de document spécifie quelles ressources (par exemple, menu, icône ou accélérateur table) sont utilisés pour ce type de document. Chaque document contient un pointeur vers lui est associée `CDocTemplate` objet.  
  
 Les utilisateurs interagissent avec un document via le [CView](../../mfc/reference/cview-class.md) ou les objets associés. Une vue affiche une image du document dans une fenêtre frame et interprète les entrées utilisateur comme des opérations sur le document. Un document peut avoir plusieurs vues associées. Lorsque l’utilisateur ouvre une fenêtre sur un document, l’infrastructure crée une vue et l’attache au document. Le modèle de document spécifie le type de vue et la fenêtre frame sont utilisées pour afficher chaque type de document.  
  
 Documents qui font partie de la norme de l’infrastructure routage des commandes et, par conséquent, recevoir des commandes à partir de composants d’interface utilisateur standard (par exemple, l’élément de menu Enregistrer). Un document reçoit des commandes transmises par la vue active. Si le document ne gère une commande donnée, il transfère la commande pour le modèle de document qui le gère.  
  
 Lorsque les données d’un document sont modifiées, chacune de ses vues doit refléter ces modifications. **CDocument** fournit le [UpdateAllViews](#updateallviews) fonction membre pour vous notifier les vues de telles modifications, pour les vues se repeindre si nécessaire. Le framework invite également l’utilisateur d’enregistrer un fichier modifié avant sa fermeture.  
  
 Pour implémenter des documents dans une application classique, vous devez procédez comme suit :  
  
-   Dérivez une classe de **CDocument** pour chaque type de document.  
  
-   Ajoutez des variables membres pour stocker les données de chaque document.  
  
-   Implémenter des fonctions membres pour la lecture et la modification des données du document. Vues du document sont les principaux utilisateurs de ces fonctions membres.  
  
-   Remplacer la [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) fonction membre dans votre classe de document pour écrire et lire les données du document vers et depuis le disque.  
  
 **CDocument** prend en charge l’envoi de votre document par courrier si la prise en charge de messagerie (MAPI) est présente. Consultez les articles [MAPI](../../mfc/mapi.md) et [prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md).  
  
 Pour plus d’informations sur **CDocument**, consultez [sérialisation](../../mfc/serialization-in-mfc.md), [rubriques sur l’Architecture Document/vue](../../mfc/document-view-architecture.md), et [création de Document/vue](../../mfc/document-view-creation.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocument`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-nameaddviewa--cdocumentaddview"></a><a name="addview"></a>CDocument::AddView  
 Appelez cette fonction pour ajouter une vue au document.  
  
```  
void AddView(CView* pView);
```  
  
### <a name="parameters"></a>Paramètres  
 `pView`  
 Pointe vers la vue en cours d’ajout.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ajoute la vue spécifiée à la liste des vues associées avec le document ; la fonction définit également le pointeur de la vue document à ce document. L’infrastructure appelle cette fonction lors de l’attachement d’un objet de vue qui vient d’être créée pour un document ; Cela se produit en réponse à une commande fichier nouveau, ouvrir le fichier ou nouvelle fenêtre ou lorsqu’une fenêtre fractionnée est fractionnée.  
  
 Appelez cette fonction uniquement si vous êtes manuellement création et attachement d’une vue. En général vous permettra l’infrastructure de relier des documents et des vues en définissant un [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objet à associer une classe de document, la classe de vue et la classe de fenêtre frame.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocViewSDI&#12;](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]  
  
##  <a name="a-namebeginreadchunksa--cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a>CDocument::BeginReadChunks  
 Initialise segment lecture.  
  
```  
virtual void BeginReadChunks ();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namecancloseframea--cdocumentcancloseframe"></a><a name="cancloseframe"></a>CDocument::CanCloseFrame  
 Appelé par l’infrastructure avant la fermeture d’une fenêtre frame affichant le document.  
  
```  
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFrame`  
 Pointe vers la fenêtre frame d’une vue associée au document.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si elle est sécurisée fermer la fenêtre frame. sinon 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut vérifie s’il existe d’autres fenêtres frame affichant le document. Si la fenêtre frame spécifié est le dernier qui affiche le document, la fonction invite l’utilisateur à enregistrer le document s’il a été modifié. Remplacez cette fonction si vous souhaitez exécuter un traitement spécial lors de la fermeture d’une fenêtre frame. Il s’agit d’une avancée substituable.  
  
##  <a name="a-namecdocumenta--cdocumentcdocument"></a><a name="cdocument"></a>CDocument::CDocument  
 Construit un **CDocument** objet.  
  
```  
CDocument();
```  
  
### <a name="remarks"></a>Notes  
 L’infrastructure gère la création d’un document pour vous. Remplacer la [OnNewDocument](#onnewdocument) fonction membre pour effectuer une initialisation sur une base par document ; cela est particulièrement important dans les applications d’interface (monodocument SDI) de document unique.  
  
##  <a name="a-nameclearchunklista--cdocumentclearchunklist"></a><a name="clearchunklist"></a>CDocument::ClearChunkList  
 Efface la liste segment.  
  
```  
virtual void ClearChunkList ();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameclearpathnamea--cdocumentclearpathname"></a><a name="clearpathname"></a>CDocument::ClearPathName  
 Efface le chemin d’accès de l’objet document.  
  
```  
virtual void ClearPathName();
```  
  
### <a name="remarks"></a>Remarques  
 Effacer le chemin d’accès d’un `CDocument` objet entraîne l’application d’inviter l’utilisateur lorsque le document est ensuite enregistré. Cela permet une **enregistrer** commande se comporte comme un **Enregistrer sous** commande.  
  
##  <a name="a-namedeletecontentsa--cdocumentdeletecontents"></a><a name="deletecontents"></a>CDocument::DeleteContents  
 Appelé par l’infrastructure pour supprimer les données du document sans détruire la **CDocument** objet lui-même.  
  
```  
virtual void DeleteContents();
```  
  
### <a name="remarks"></a>Notes  
 Il est appelé juste avant que le document doit être détruit. Il est également appelé pour s’assurer qu’un document est vide avant qu’elle soit réutilisée. Cela est particulièrement important pour une application SDI, qui utilise un seul document ; le document est réutilisé à chaque fois que l’utilisateur crée ou ouvre un autre document. Appelez cette fonction pour implémenter une « Modifier Effacer tout » ou une commande similaire qui supprime toutes les données du document. L’implémentation par défaut de cette fonction est sans effet. Remplacez cette fonction pour supprimer les données dans votre document.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#57;](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]  
  
##  <a name="a-namefindchunka--cdocumentfindchunk"></a><a name="findchunk"></a>CDocument::FindChunk  
 Recherche d’un segment avec un GUID spécifié.  
  
```  
virtual POSITION FindChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Paramètres  
 `guid`  
 Spécifie le GUID d’un segment à rechercher.  
  
 `pid`  
 Spécifie un PID d’un segment à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Position dans la liste segment interne en cas de réussite. Dans le cas contraire `NULL`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetadaptera--cdocumentgetadapter"></a><a name="getadapter"></a>CDocument::GetAdapter  
 Retourne un pointeur vers un objet qui implémente le `IDocument` interface.  
  
```  
virtual ATL::IDocument* GetAdapter();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un objet qui implémente le `IDocument` interface.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetdoctemplatea--cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a>CDocument::GetDocTemplate  
 Appelez cette fonction pour obtenir un pointeur vers le modèle de document pour ce type de document.  
  
```  
CDocTemplate* GetDocTemplate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le modèle de document pour ce type de document, ou **NULL** si le document n’est pas géré par un modèle de document.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#58;](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]  
  
##  <a name="a-namegetfilea--cdocumentgetfile"></a><a name="getfile"></a>CDocument::GetFile  
 Appelez cette fonction membre pour obtenir un pointeur vers un `CFile` objet.  
  
```  
virtual CFile* GetFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 Chaîne qui est le chemin d’accès au fichier souhaité. Le chemin d’accès peut être relatif ou absolu.  
  
 `pError`  
 Pointeur vers un objet existant à l’exception du fichier qui indique l’état d’achèvement de l’opération.  
  
 `nOpenFlags`  
 Mode de partage et d’accès. Spécifie l’action à entreprendre lors de l’ouverture du fichier. Vous pouvez combiner les options répertoriées dans le constructeur CFile [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) à l’aide de l’opérateur de bits OR (opérateur) (|). L’autorisation d’un accès et un partage sont requis ; le **modeCreate** et **modeNoInherit** modes sont facultatifs.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CFile` objet.  
  
##  <a name="a-namegetfirstviewpositiona--cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a>CDocument::GetFirstViewPosition  
 Appelez cette fonction pour obtenir la position de la première vue dans la liste des vues associées au document.  
  
```  
virtual POSITION GetFirstViewPosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui peut être utilisé pour l’itération avec la [GetNextView](#getnextview) fonction membre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetnextviewa--cdocumentgetnextview"></a><a name="getnextview"></a>CDocument::GetNextView  
 Appelez cette fonction pour effectuer une itération dans toutes les vues du document.  
  
```  
virtual CView* GetNextView(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `rPosition`  
 Une référence à un **POSITION** valeur retournée par un appel précédent à la `GetNextView` ou [GetFirstViewPosition](#getfirstviewposition) les fonctions membres. Cette valeur ne doit pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la vue identifié par `rPosition`.  
  
### <a name="remarks"></a>Remarques  
 La fonction retourne la vue identifiée par `rPosition` et définit ensuite `rPosition` à la **POSITION** la valeur de la vue suivante dans la liste. Si la vue récupérée est le dernier dans la liste, puis `rPosition` a **NULL**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#59;](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]  
  
##  <a name="a-namegetpathnamea--cdocumentgetpathname"></a><a name="getpathname"></a>CDocument::GetPathName  
 Appelez cette fonction pour obtenir le chemin d’accès complet du fichier de disque du document.  
  
```  
const CString& GetPathName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chemin d’accès complet du document. Cette chaîne est vide si le document n’a pas été enregistré ou n’a pas un fichier de disque associé.  
  
##  <a name="a-namegetthumbnaila--cdocumentgetthumbnail"></a><a name="getthumbnail"></a>CDocument::GetThumbnail  
 Crée une image bitmap à utiliser par le fournisseur de miniatures pour afficher la miniature.  
  
```  
virtual BOOL GetThumbnail(
    UINT cx,  
    HBITMAP* phbmp,  
    DWORD* pdwAlpha);
```  
  
### <a name="parameters"></a>Paramètres  
 `cx`  
 Spécifie la largeur et la hauteur de la bitmap.  
  
 `phbmp`  
 Contient un handle vers une bitmap, lorsque la fonction est retournée avec succès.  
  
 `pdwAlpha`  
 Contient une valeur DWORD spécifiant la valeur du canal alpha, lorsque la fonction est retournée avec succès.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si une image bitmap de la miniature a été créée avec succès ; sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegettitlea--cdocumentgettitle"></a><a name="gettitle"></a>CDocument::GetTitle  
 Appelez cette fonction pour obtenir le titre du document, qui est généralement dérivé de nom de fichier du document.  
  
```  
const CString& GetTitle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le titre du document.  
  
##  <a name="a-nameinitializesearchcontenta--cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a>CDocument::InitializeSearchContent  
 Appelée pour initialiser le contenu de recherche pour le Gestionnaire de recherche.  
  
```  
virtual void InitializeSearchContent ();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode dans une classe dérivée pour initialiser le contenu de recherche. Le contenu doit être une chaîne délimitée par des parties de « ; ». Par exemple, « point ; rectangle ; élément OLE ».  
  
##  <a name="a-nameismodifieda--cdocumentismodified"></a><a name="ismodified"></a>CDocument::IsModified  
 Appelez cette fonction pour déterminer si le document a été modifié depuis son dernier enregistrement.  
  
```  
virtual BOOL IsModified();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document a été modifié depuis son dernier enregistrement ; sinon 0.  
  
##  <a name="a-nameissearchandorganizehandlera--cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a>CDocument::IsSearchAndOrganizeHandler  
 Indique si cette instance de `CDocument` a été créé pour le Gestionnaire de recherche s’organiser.  
  
```  
BOOL IsSearchAndOrganizeHandler() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si cette instance de `CDocument` a été créé pour le Gestionnaire de recherche s’organiser.  
  
### <a name="remarks"></a>Remarques  
 Actuellement, cette fonction retourne `TRUE` uniquement pour les gestionnaires d’aperçu détaillé implémentés dans un serveur de traitement à l’emploi. Vous pouvez définir les indicateurs appropriés (m_bPreviewHandlerMode, m_bSearchMode, m_bGetThumbnailMode) au niveau de votre application à rendre cette fonction retour `TRUE`.  
  
##  <a name="a-nameloaddocumentfromstreama--cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a>CDocument::LoadDocumentFromStream  
 Appelée pour charger les données du document à partir d’un flux de données.  
  
```  
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,  
    DWORD dwGrfMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 Pointeur vers un flux de données. Ce flux est fourni par l’interpréteur de commandes.  
  
 `dwGrfMode`  
 Mode d’accès au flux.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération de chargement réussit, sinon HRESULT avec un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez substituer cette méthode dans une classe dérivée pour personnaliser le chargement des données à partir du flux.  
  
##  <a name="a-namembgetthumbnailmodea--cdocumentmbgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a>CDocument::m_bGetThumbnailMode  
 Spécifie que le `CDocument` objet a été créé par dllhost pour les miniatures. Doivent être archivés `CView::OnDraw`.  
  
```  
BOOL m_bGetThumbnailMode;  
```  
  
### <a name="remarks"></a>Remarques  
 `TRUE`Indique que le document a été créé par dllhost pour les miniatures.  
  
##  <a name="a-namembpreviewhandlermodea--cdocumentmbpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a>CDocument::m_bPreviewHandlerMode  
 Spécifie que le `CDocument` objet a été créé par prevhost pour l’aperçu riche. Doivent être archivés `CView::OnDraw`.  
  
```  
BOOL m_bPreviewHandlerMode;  
```  
  
### <a name="remarks"></a>Remarques  
 `TRUE`Indique que le document a été créé par prevhost pour l’aperçu riche.  
  
##  <a name="a-namembsearchmodea--cdocumentmbsearchmode"></a><a name="m_bsearchmode"></a>CDocument::m_bSearchMode  
 Spécifie que le `CDocument` objet a été créé par un indexeur, ou par une autre application de recherche.  
  
```  
BOOL m_bSearchMode;  
```  
  
### <a name="remarks"></a>Remarques  
 `TRUE`Indique que le document a été créé par un indexeur, ou par une autre application de recherche.  
  
##  <a name="a-namemclrrichpreviewbackcolora--cdocumentmclrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a>CDocument::m_clrRichPreviewBackColor  
 Spécifie la couleur d’arrière-plan de la fenêtre d’aperçu détaillé. Cette couleur est définie par l’hôte.  
  
```  
COLORREF m_clrRichPreviewBackColor;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namemclrrichpreviewtextcolora--cdocumentmclrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a>CDocument::m_clrRichPreviewTextColor  
 Spécifie la couleur de premier plan de la fenêtre d’aperçu détaillé. Cette couleur est définie par l’hôte.  
  
```  
COLORREF m_clrRichPreviewTextColor;  
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemlfrichpreviewfonta--cdocumentmlfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a>CDocument::m_lfRichPreviewFont  
 Spécifie la police du texte de la fenêtre d’aperçu détaillé. Ces informations de police sont définies par l’hôte.  
  
```  
CFont m_lfRichPreviewFont;  
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonbeforerichpreviewfontchangeda--cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a>CDocument::OnBeforeRichPreviewFontChanged  
 Appelé avant la modification de la police de l’aperçu détaillé.  
  
```  
virtual void OnBeforeRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonchangedviewlista--cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a>CDocument::OnChangedViewList  
 Appelé par le framework après qu’une vue est ajoutée ou supprimée du document.  
  
```  
virtual void OnChangedViewList();
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction vérifie si la dernière vue est supprimée et, si tel est le cas, supprime le document. Remplacez cette fonction si vous souhaitez exécuter un traitement spécial lorsque le framework ajoute ou supprime une vue. Par exemple, si vous souhaitez restent ouverts même lorsqu’aucune vue attaché, remplacez cette fonction.  
  
##  <a name="a-nameonclosedocumenta--cdocumentonclosedocument"></a><a name="onclosedocument"></a>CDocument::OnCloseDocument  
 Appelé par l’infrastructure lorsque le document est fermé, dans le cadre de la commande.  
  
```  
virtual void OnCloseDocument();
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction supprime tous les cadres utilisés pour afficher le document, ferme la vue, nettoie le contenu du document et appelle le [DeleteContents](#deletecontents) fonction membre à supprimer les données du document.  
  
 Remplacez cette fonction si vous souhaitez traiter un nettoyage spécial lorsque le framework ferme un document. Par exemple, si le document représente un enregistrement dans une base de données, vous souhaiterez peut-être de remplacer cette fonction pour fermer la base de données. Vous devez appeler la version classe de base de cette fonction à partir de votre remplacement.  
  
##  <a name="a-nameoncreatepreviewframea--cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a>CDocument::OnCreatePreviewFrame  
 Appelé par l’infrastructure lorsqu’il a besoin créer une image d’aperçu pour l’aperçu riche.  
  
```  
virtual BOOL OnCreatePreviewFrame();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` si le frame est créé avec succès ; sinon `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameondocumenteventa--cdocumentondocumentevent"></a><a name="ondocumentevent"></a>CDocument::OnDocumentEvent  
 Appelé par l’infrastructure en réponse à un événement de document.  
  
```  
virtual void OnDocumentEvent(DocumentEvent deEvent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `deEvent`  
 Type de données énuméré qui décrit le type d’événement.  
  
### <a name="remarks"></a>Notes  
 Événements de document peuvent affecter plusieurs classes. Cette méthode est chargée pour la gestion des événements de document qui affectent les classes autres que la [CDocument (classe)](../../mfc/reference/cdocument-class.md). Actuellement, la seule classe qui doit répondre aux événements de document est la [CDataRecoveryHandler classe](../../mfc/reference/cdatarecoveryhandler-class.md). Le `CDocument` classe a des autres méthodes remplaçables chargés de gérer l’effet sur le `CDocument`.  
  
 Le tableau suivant répertorie les valeurs possibles pour `deEvent` et les événements qu’elles correspondent aux.  
  
|Valeur|Événement correspondant|  
|-----------|-------------------------|  
|`onAfterNewDocument`|Un nouveau document a été créé.|  
|`onAfterOpenDocument`|Un nouveau document a été ouvert.|  
|`onAfterSaveDocument`|Le document a été enregistré.|  
|`onAfterCloseDocument`|Le document a été fermé.|  
  
##  <a name="a-nameondrawthumbnaila--cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a>CDocument::OnDrawThumbnail  
 Substituez cette méthode dans une classe dérivée pour dessiner la miniature.  
  
```  
virtual void OnDrawThumbnail(
    CDC& dc,  
    LPRECT lprcBounds);
```  
  
### <a name="parameters"></a>Paramètres  
 `dc`  
 Une référence à un contexte de périphérique.  
  
 `lprcBounds`  
 Spécifie un rectangle englobant de la zone où la miniature doit être dessinée.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonfilesendmaila--cdocumentonfilesendmail"></a><a name="onfilesendmail"></a>CDocument::OnFileSendMail  
 Envoie un message via l’hôte de messagerie résident (le cas échéant) dans le document en tant que pièce jointe.  
  
```  
void OnFileSendMail();
```  
  
### <a name="remarks"></a>Remarques  
 `OnFileSendMail`appels [OnSaveDocument](#onsavedocument) pour sérialiser (des documents sans titre et modifiés dans un fichier temporaire, qui est ensuite envoyé par courrier électronique Enregistrer). Si le document n’a pas été modifié, un fichier temporaire n’est pas nécessaire ; l’original est envoyé. `OnFileSendMail`charge MAPI32. DLL s’il n’a pas déjà été chargé.  
  
 Une implémentation particulière de `OnFileSendMail` de [COleDocument](../../mfc/reference/coledocument-class.md) gère correctement les fichiers composés.  
  
 **CDocument** prend en charge l’envoi de votre document par courrier si la prise en charge de messagerie (MAPI) est présente. Consultez les articles [MAPI rubriques](../../mfc/mapi.md) et [prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameonloaddocumentfromstreama--cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a>CDocument::OnLoadDocumentFromStream  
 Appelé par l’infrastructure lorsqu’il a besoin charger les données du document à partir d’un flux de données.  
  
```  
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,  
    DWORD grfMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 Pointeur vers un flux entrant.  
  
 `grfMode`  
 Mode d’accès au flux.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si le chargement a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonnewdocumenta--cdocumentonnewdocument"></a><a name="onnewdocument"></a>CDocument::OnNewDocument  
 Appelé par l’infrastructure dans le cadre de la commande fichier nouveau.  
  
```  
virtual BOOL OnNewDocument();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document a été initialisé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction appelle le [DeleteContents](#deletecontents) fonction membre pour vous assurer que le document est vide et le nouveau document en tant que nouvelle marque. Remplacez cette fonction pour initialiser la structure de données pour un nouveau document. Vous devez appeler la version classe de base de cette fonction à partir de votre remplacement.  
  
 Si l’utilisateur choisit la commande nouveau fichier dans une application SDI, l’infrastructure utilise cette fonction pour réinitialiser le document existant, plutôt que de créer un nouveau. Si l’utilisateur choisit le nouveau fichier dans une application d’interface (multidocument MDI) document multiples, l’infrastructure crée un nouveau document à chaque fois, puis appelle cette fonction pour initialiser. Vous devez placer votre code d’initialisation dans cette fonction plutôt que dans le constructeur de la commande fichier nouveau pour être efficaces dans les applications SDI.  
  
 Notez que les cas où `OnNewDocument` est appelée deux fois. Cela se produit lorsque le document est incorporé en tant qu’un serveur de documents ActiveX. La fonction est d’abord appelée le `CreateInstance` (méthode) (exposé par le `COleObjectFactory`-classe dérivée) et une deuxième fois par le `InitNew` (méthode) (exposé par le `COleServerDoc`-classe dérivée).  
  
### <a name="example"></a>Exemple  
 Les exemples suivants illustrent d’autres méthodes de l’initialisation d’un objet document.  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
##  <a name="a-nameonopendocumenta--cdocumentonopendocument"></a><a name="onopendocument"></a>CDocument::OnOpenDocument  
 Appelé par l’infrastructure dans le cadre de la commande Ouvrir un fichier.  
  
```  
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Pointe vers le chemin d’accès du document à ouvrir.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document a été chargé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction ouvre le fichier spécifié, appelle le [DeleteContents](#deletecontents) fonction membre pour vous assurer que le document est vide, appelle [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) pour lire le fichier de contenu et marque le document en tant que nouvelle. Remplacez cette fonction si vous souhaitez utiliser un élément autre que le mécanisme d’archivage ou le fichier. Par exemple, vous pouvez écrire une application où les documents représentent les enregistrements dans une base de données plutôt que des fichiers distincts.  
  
 Si l’utilisateur choisit la commande Ouvrir dans une application SDI, l’infrastructure utilise cette fonction pour réinitialiser existant **CDocument** objet, plutôt que de créer un nouveau. Si l’utilisateur choisit ouvrir le fichier dans une application MDI, l’infrastructure construit une nouvelle **CDocument** objet chaque fois, puis appelle cette fonction pour l’initialiser. Vous devez placer votre code d’initialisation dans cette fonction plutôt que dans le constructeur de la commande Ouvrir un fichier pour être efficaces dans les applications SDI.  
  
### <a name="example"></a>Exemple  
 Les exemples suivants illustrent d’autres méthodes de l’initialisation d’un objet document.  
  
 [!code-cpp[NVC_MFCDocView&#60;](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#61;](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#62;](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#63;](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]  
  
##  <a name="a-nameonpreviewhandlerqueryfocusa--cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a>CDocument::OnPreviewHandlerQueryFocus  
 Dirige le Gestionnaire d’aperçus pour retourner le HWND récupérées à partir de l’appel du `GetFocus` fonction.  
  
```  
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `phwnd`  
 [out] Lorsque cette méthode est retournée, contient un pointeur vers le HWND retourné en appelant le `GetFocus` fonction à partir du thread de premier plan du Gestionnaire d’aperçus.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si l’opération a réussi ; ou une valeur d’erreur dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonpreviewhandlertranslateacceleratora--cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a>CDocument::OnPreviewHandlerTranslateAccelerator  
 Dirige le Gestionnaire d’aperçus pour gérer une séquence de touches transmis par la pompe de messages du processus dans lequel s’exécute le Gestionnaire d’aperçus.  
  
```  
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```  
  
### <a name="parameters"></a>Paramètres  
 `pmsg`  
 [in] Pointeur vers un message de fenêtre.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le message de séquence de touches peut être traité par le Gestionnaire d’aperçus, le gestionnaire traite et retourne S_OK. Si le Gestionnaire d’aperçus ne peut pas traiter le message de séquence de touches, il l’offre à l’hôte via `IPreviewHandlerFrame::TranslateAccelerator`. Si l’hôte traite le message, cette méthode retourne S_OK. Si l’hôte ne traite pas le message, cette méthode retourne S_FALSE.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonrichpreviewbackcolorchangeda--cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a>CDocument::OnRichPreviewBackColorChanged  
 Appelé lorsque la couleur d’arrière-plan aperçu détaillé a changé.  
  
```  
virtual void OnRichPreviewBackColorChanged();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonrichpreviewfontchangeda--cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a>CDocument::OnRichPreviewFontChanged  
 Appelé lorsque la police aperçu détaillé a changé.  
  
```  
virtual void OnRichPreviewFontChanged();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonrichpreviewsitechangeda--cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a>CDocument::OnRichPreviewSiteChanged  
 Appelé lorsque le site d’aperçu détaillé a changé.  
  
```  
virtual void OnRichPreviewSiteChanged();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonrichpreviewtextcolorchangeda--cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a>CDocument::OnRichPreviewTextColorChanged  
 Appelé lorsque la couleur du texte enrichi Aperçu a été modifiée.  
  
```  
virtual void OnRichPreviewTextColorChanged();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonsavedocumenta--cdocumentonsavedocument"></a><a name="onsavedocument"></a>CDocument::OnSaveDocument  
 Appelé par l’infrastructure dans le cadre de la commande Enregistrer ou enregistrer sous.  
  
```  
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Pointe vers le chemin d’accès complet vers lequel le fichier doit être enregistré.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document a été enregistré avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction ouvre le fichier spécifié, les appels [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) pour écrire les données du document dans le fichier, puis marque le document comme nettoyer. Remplacez cette fonction si vous souhaitez exécuter un traitement spécial lorsque le framework enregistre un document. Par exemple, vous pouvez écrire une application où les documents représentent les enregistrements dans une base de données plutôt que des fichiers distincts.  
  
##  <a name="a-nameonunloadhandlera--cdocumentonunloadhandler"></a><a name="onunloadhandler"></a>CDocument::OnUnloadHandler  
 Appelé par l’infrastructure lorsque le Gestionnaire d’aperçus est déchargé.  
  
```  
virtual void OnUnloadHandler();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonupdatefilesendmaila--cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a>CDocument::OnUpdateFileSendMail  
 Permet la **ID_FILE_SEND_MAIL** commande si la prise en charge de messagerie (MAPI) est présente.  
  
```  
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers le [CCmdUI](../../mfc/reference/ccmdui-class.md) objet associé à la **ID_FILE_SEND_MAIL** commande.  
  
### <a name="remarks"></a>Remarques  
 Dans le cas contraire, la fonction supprime le **ID_FILE_SEND_MAIL** commande dans le menu, y compris les séparateurs ci-dessus ou le menu éléments selon les besoins. MAPI est activé si MAPI32. DLL est présent dans le chemin d’accès et, dans la section [Mail] du fichier WIN. Fichier INI, MAPI =&1;. La plupart des applications placer cette commande dans le menu fichier.  
  
 **CDocument** prend en charge l’envoi de votre document par courrier si la prise en charge de messagerie (MAPI) est présente. Consultez les articles [MAPI rubriques](../../mfc/mapi.md) et [prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md).  
  
##  <a name="a-nameprecloseframea--cdocumentprecloseframe"></a><a name="precloseframe"></a>CDocument::PreCloseFrame  
 Cette fonction membre est appelée par l’infrastructure avant la destruction de la fenêtre frame.  
  
```  
virtual void PreCloseFrame(CFrameWnd* pFrame);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFrame`  
 Pointeur vers le [CFrameWnd](../../mfc/reference/cframewnd-class.md) qui contient le texte associé **CDocument** objet.  
  
### <a name="remarks"></a>Remarques  
 Il peut être substituée pour fournir un nettoyage personnalisé, mais veillez à appeler la classe de base.  
  
 La valeur par défaut de `PreCloseFrame` n’a aucun effet **CDocument**. Le **CDocument**-classes dérivées [COleDocument](../../mfc/reference/coledocument-class.md) et [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) utiliser cette fonction membre.  
  
##  <a name="a-namereadnextchunkvaluea--cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a>CDocument::ReadNextChunkValue  
 Lit la valeur de segment suivante.  
  
```  
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppValue`  
 [out] Lorsque la fonction retourne une valeur, `ppValue` contient la valeur qui a été lu.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namereleasefilea--cdocumentreleasefile"></a><a name="releasefile"></a>CDocument::ReleaseFile  
 Cette fonction membre est appelée par l’infrastructure pour la version d’un fichier, ce qui rend disponible pour une utilisation par d’autres applications.  
  
```  
virtual void ReleaseFile(
    CFile* pFile,  
    BOOL bAbort);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFile`  
 Pointeur vers l’objet CFile soit libéré.  
  
 `bAbort`  
 Spécifie si le fichier doit être publié à l’aide `CFile::Close` ou `CFile::Abort`. **FALSE** si le fichier doit être publié à l’aide de [CFile::Close](../../mfc/reference/cfile-class.md#close); **TRUE** si le fichier doit être publié à l’aide de [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="remarks"></a>Notes  
 Si `bAbort` est **TRUE**, `ReleaseFile` appelle `CFile::Abort`, et le fichier est publié. `CFile::Abort`pas lèvera une exception.  
  
 Si `bAbort` est **FALSE**, `ReleaseFile` appelle `CFile::Close` et le fichier est publié.  
  
 Remplacez cette fonction membre pour demander une action de l’utilisateur avant la publication du fichier.  
  
##  <a name="a-nameremovechunka--cdocumentremovechunk"></a><a name="removechunk"></a>CDocument::RemoveChunk  
 Supprime un segment avec le GUID spécifié.  
  
```  
virtual void RemoveChunk(
    REFCLSID guid,  
    DWORD pid);
```  
  
### <a name="parameters"></a>Paramètres  
 `Guid`  
 Spécifie le GUID d’un segment à supprimer.  
  
 `Pid`  
 Spécifie le PID d’un segment à supprimer.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameremoveviewa--cdocumentremoveview"></a><a name="removeview"></a>CDocument::RemoveView  
 Appelez cette fonction pour détacher une vue à partir d’un document.  
  
```  
void RemoveView(CView* pView);
```  
  
### <a name="parameters"></a>Paramètres  
 `pView`  
 Pointe vers la vue en cours de suppression.  
  
### <a name="remarks"></a>Notes  
 Cette fonction supprime l’affichage spécifié dans la liste des vues associées avec le document ; Il définit également pointeur de document de l’affichage sur **NULL**. Cette fonction est appelée par l’infrastructure lors de la fermeture d’une fenêtre frame ou d’un volet d’une fenêtre fractionnée est fermé.  
  
 Appelez cette fonction uniquement si vous sont détacher manuellement d’une vue. En général vous permettra l’infrastructure de détacher des documents et des vues en définissant un [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) objet à associer une classe de document, la classe de vue et la classe de fenêtre frame.  
  
 Consultez l’exemple [AddView](#addview) pour un exemple d’implémentation.  
  
##  <a name="a-namereportsaveloadexceptiona--cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a>CDocument::ReportSaveLoadException  
 Appelée si une exception est levée (généralement un [CFileException](../../mfc/reference/cfileexception-class.md) ou [exception CArchiveException](../../mfc/reference/carchiveexception-class.md)) lors de l’enregistrement ou chargement du document.  
  
```  
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,  
    CException* e,  
    BOOL bSaving,  
    UINT nIDPDefault);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Pointe vers le nom du document qui était en cours d’enregistrement ou chargement.  
  
 *e*  
 Points à l’exception qui a été levée. Peut être **NULL**.  
  
 *benregistrement des*  
 Indicateur signalant que l’opération était en cours ; différent de zéro si le document a été sauvegardé, 0 si le document a été chargé.  
  
 `nIDPDefault`  
 Identificateur du message d’erreur à afficher si la fonction ne spécifie pas plus spécifique.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut examine l’objet exception et recherche un message d’erreur qui décrit précisément la cause. Si un message spécifique est introuvable ou si *e* est **NULL**, le message général spécifié par le `nIDPDefault` paramètre est utilisé. Ensuite, la fonction affiche une boîte de message contenant le message d’erreur. Remplacez cette fonction si vous souhaitez fournir des messages d’échec supplémentaire et personnalisé. Il s’agit d’une avancée substituable.  
  
##  <a name="a-namesavemodifieda--cdocumentsavemodified"></a><a name="savemodified"></a>CDocument::SaveModified  
 Appelé par l’infrastructure avant de se fermer un document modifié.  
  
```  
virtual BOOL SaveModified();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si elle est sécurisée continuer, fermez le document. 0 si le document ne doit pas être fermé.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut de cette fonction affiche une boîte de message demandant à l’utilisateur s’il faut enregistrer les modifications dans le document, si les ont été apportées. Remplacez cette fonction si votre programme nécessite une autre procédure invite. Il s’agit d’une avancée substituable.  
  
##  <a name="a-namesetchunkvaluea--cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a>CDocument::SetChunkValue  
 Définit une valeur de segment.  
  
```  
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `pValue`  
 Spécifie une valeur de segment à définir.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetmodifiedflaga--cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a>CDocument::SetModifiedFlag  
 Appelez cette fonction après avoir apporté des modifications au document.  
  
```  
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bModified`  
 Indicateur signalant si le document a été modifié.  
  
### <a name="remarks"></a>Remarques  
 En appelant cette fonction de manière cohérente, vous vérifiez que le framework invite l’utilisateur à enregistrer les modifications avant de fermer un document. En général, vous devez utiliser la valeur par défaut **TRUE** pour la `bModified` paramètre. Pour marquer un document plus « propre » (non modifié), appelez cette fonction avec la valeur **FALSE**.  
  
##  <a name="a-namesetpathnamea--cdocumentsetpathname"></a><a name="setpathname"></a>CDocument::SetPathName  
 Appelez cette fonction pour spécifier le chemin d’accès complet du fichier de disque du document.  
  
```  
virtual void SetPathName(
    LPCTSTR lpszPathName,  
    BOOL bAddToMRU = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Pointe vers la chaîne à utiliser en tant que le chemin d’accès pour le document.  
  
 `bAddToMRU`  
 Détermine si le nom de fichier est ajouté à l’utilisés le plus récemment liste (MRU). Si **TRUE,** le nom de fichier est ajoutée ; si **FALSE**, il n’est pas ajouté.  
  
### <a name="remarks"></a>Notes  
 Selon la valeur de `bAddToMRU` le chemin d’accès est ajoutée ou pas ajouté à la liste des derniers fichiers utilisés gérée par l’application. Notez que certains documents ne sont pas associés à un fichier de disque. Appelez cette fonction uniquement si vous substituez l’implémentation par défaut pour ouvrir et enregistrer des fichiers utilisés par l’infrastructure.  
  
##  <a name="a-namesettitlea--cdocumentsettitle"></a><a name="settitle"></a>CDocument::SetTitle  
 Appelez cette fonction pour spécifier le titre du document (la chaîne affichée dans la barre de titre d’une fenêtre frame).  
  
```  
virtual void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTitle`  
 Pointe vers la chaîne à utiliser comme le titre du document.  
  
### <a name="remarks"></a>Notes  
 Appel de cette fonction met à jour les titres de toutes les fenêtres frame qui affichent le document.  
  
##  <a name="a-nameupdateallviewsa--cdocumentupdateallviews"></a><a name="updateallviews"></a>CDocument::UpdateAllViews  
 Appelez cette fonction une fois que le document a été modifié.  
  
```  
void UpdateAllViews(
    CView* pSender,  
    LPARAM lHint = 0L,  
    CObject* pHint = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSender`  
 Pointe vers la vue qui a modifié le document, ou **NULL** si toutes les vues doivent être mis à jour.  
  
 `lHint`  
 Contient des informations sur la modification.  
  
 `pHint`  
 Pointe vers un objet stockant des informations sur la modification.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler cette fonction après avoir appelé la [SetModifiedFlag](#setmodifiedflag) fonction membre. Cette fonction informe chaque vue associée au document, à l’exception de l’affichage spécifié par `pSender`, que le document a été modifié. En général, vous appelez cette fonction à partir de votre classe d’affichage une fois que l’utilisateur a modifié le document dans une vue.  
  
 Cette fonction appelle le [CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate) afficher de la fonction membre pour chacune des vues du document à l’exception de l’envoi, en passant `pHint` et `lHint`. Utilisez ces paramètres pour passer des informations aux vues sur les modifications apportées au document. Vous pouvez encoder à l’aide des informations `lHint` ou vous pouvez définir un [CObject](../../mfc/reference/cobject-class.md)-classe dérivée stockent des informations sur les modifications et passer un objet de cette classe à l’aide de `pHint`. Remplacer la `CView::OnUpdate` fonction membre dans votre [CView](../../mfc/reference/cview-class.md)-classe afin d’optimiser la mise à jour de l’affichage de la vue en fonction des informations passées dérivée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#64;](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC MDIDOCVW](../../visual-cpp-samples.md)   
 [Exemple MFC SNAPVW](../../visual-cpp-samples.md)   
 [Exemple MFC NPP](../../visual-cpp-samples.md)   
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CCmdTarget (classe)](../../mfc/reference/ccmdtarget-class.md)   
 [CView (classe)](../../mfc/reference/cview-class.md)   
 [CDocTemplate (classe)](../../mfc/reference/cdoctemplate-class.md)

