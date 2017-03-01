---
title: Classe COleDocument | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDocument
dev_langs:
- C++
helpviewer_keywords:
- COleDocument class
- OLE documents, base class
- OLE containers, client items
- visual editing, OLE document base class
- OLE documents
- documents, OLE
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
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
ms.openlocfilehash: 73bd1bc5c2c93e180b42a79cf23ab98360887c31
ms.lasthandoff: 02/24/2017

---
# <a name="coledocument-class"></a>COleDocument (classe)
Classe de base des documents OLE qui prennent en charge la modification sur place.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleDocument : public CDocument  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDocument::COleDocument](#coledocument)|Construit un objet `COleDocument`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDocument::AddItem](#additem)|Ajoute un élément à la liste des éléments gérés par le document.|  
|[COleDocument::ApplyPrintDevice](#applyprintdevice)|Définit le périphérique d’impression pour tous les éléments de client dans le document.|  
|[COleDocument::EnableCompoundFile](#enablecompoundfile)|Génère des documents soient enregistrés en utilisant le format de fichier de stockage structuré OLE.|  
|[COleDocument::GetInPlaceActiveItem](#getinplaceactiveitem)|Retourne l’élément OLE est actif actuellement en place.|  
|[COleDocument::GetNextClientItem](#getnextclientitem)|Obtient l’élément suivant de client pour l’itération.|  
|[COleDocument::GetNextItem](#getnextitem)|Obtient l’élément de document suivant pour l’itération.|  
|[COleDocument::GetNextServerItem](#getnextserveritem)|Obtient l’élément suivant du serveur pour l’itération.|  
|[COleDocument::GetPrimarySelectedItem](#getprimaryselecteditem)|Retourne l’élément OLE principal sélectionné dans le document.|  
|[COleDocument::GetStartPosition](#getstartposition)|Obtient la position initiale pour commencer l’itération.|  
|[COleDocument::HasBlankItems](#hasblankitems)|Vérifie les éléments vides dans le document.|  
|[COleDocument::OnShowViews](#onshowviews)|Appelé lorsque le document est visible ou invisible.|  
|[COleDocument::RemoveItem](#removeitem)|Supprime un élément de la liste des éléments gérés par le document.|  
|[COleDocument::UpdateModifiedFlag](#updatemodifiedflag)|Marque le document comme modifiée si un des éléments OLE contenus ont été modifié.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[COleDocument::OnEditChangeIcon](#oneditchangeicon)|Gère les événements de la commande de menu changer d’icône.|  
|[COleDocument::OnEditConvert](#oneditconvert)|Gère la conversion d’un objet incorporé ou lié à partir d’un type à un autre.|  
|[COleDocument::OnEditLinks](#oneditlinks)|Gère les événements de la commande liaisons dans le menu Edition.|  
|[COleDocument::OnFileSendMail](#onfilesendmail)|Envoie un message électronique avec le document joint.|  
|[COleDocument::OnUpdateEditChangeIcon](#onupdateeditchangeicon)|Appelé par l’infrastructure pour mettre à jour l’interface utilisateur de commande pour l’option de menu modifier/changer d’icône.|  
|[COleDocument::OnUpdateEditLinksMenu](#onupdateeditlinksmenu)|Appelé par l’infrastructure pour mettre à jour l’interface utilisateur de commande pour l’option de menu/Modifier les liens.|  
|[COleDocument::OnUpdateObjectVerbMenu](#onupdateobjectverbmenu)|Appelé par l’infrastructure de mise à jour de la commande de l’interface utilisateur pour la modification / *ObjectName* option de menu et le sous-menu verbe accédé à partir de modifier / *ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](#onupdatepastelinkmenu)|Appelé par l’infrastructure pour mettre à jour l’interface utilisateur de commande pour l’option de menu Collage spécial.|  
|[COleDocument::OnUpdatePasteMenu](#onupdatepastemenu)|Appelé par l’infrastructure pour mettre à jour l’interface utilisateur de commande pour l’option de menu Coller.|  
  
## <a name="remarks"></a>Remarques  
 `COleDocument`est dérivé **CDocument**, ce qui permet à vos applications OLE à utiliser l’architecture document/vue fournie par la bibliothèque Microsoft Foundation Class.  
  
 `COleDocument`traite un document comme une collection de [CDocItem](../../mfc/reference/cdocitem-class.md) objets pour traiter les éléments OLE. Applications conteneur et serveur requièrent une telle architecture, car leurs documents doivent être en mesure de contenir des éléments OLE. Le [COleServerItem](../../mfc/reference/coleserveritem-class.md) et [COleClientItem](../../mfc/reference/coleclientitem-class.md) des classes, tous deux dérivés de `CDocItem`, gérer les interactions entre les applications et des éléments OLE.  
  
 Si vous écrivez une application conteneur simple, dérivez votre classe de document de `COleDocument`. Si vous écrivez une application de conteneur qui prend en charge la liaison aux éléments incorporés contenues par ses documents, dérivez votre classe de document de [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md). Si vous écrivez un serveur d’application ou combinaison conteneur/serveur, dérivez votre classe de document de [COleServerDoc](../../mfc/reference/coleserverdoc-class.md). `COleLinkingDoc`et `COleServerDoc` sont dérivés de `COleDocument`, de sorte que ces classes héritent de tous les services disponibles dans `COleDocument` et **CDocument**.  
  
 Pour utiliser `COleDocument`, dérivez une classe à partir de celui-ci et ajoutez des fonctionnalités pour gérer de l’application données non OLE, ainsi que des éléments liés ou incorporés. Si vous définissez `CDocItem`-les classes dérivées pour stocker les données de l’application native, vous pouvez utiliser l’implémentation par défaut définie par `COleDocument` stocker votre OLE et les données non-OLE. Vous pouvez également concevoir vos propres structures de données pour le stockage des données non-OLE séparément à partir des éléments OLE. Pour plus d’informations, consultez l’article [conteneurs : fichiers composés](../../mfc/containers-compound-files.md)...  
  
 **CDocument** prend en charge l’envoi de votre document par courrier si la prise en charge de messagerie (MAPI) est présente. `COleDocument`a mis à jour [OnFileSendMail](#onfilesendmail) pour gérer correctement les documents composés. Pour plus d’informations, consultez les articles [MAPI](../../mfc/mapi.md) et [prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md)...  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxole.h  
  
##  <a name="a-nameadditema--coledocumentadditem"></a><a name="additem"></a>COleDocument::AddItem  
 Appelez cette fonction pour ajouter un élément dans le document.  
  
```  
virtual void AddItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément de document.  
  
### <a name="remarks"></a>Remarques  
 Vous n’avez pas besoin d’appeler explicitement cette fonction lorsqu’elle est appelée par le `COleClientItem` ou `COleServerItem` constructeur qui accepte un pointeur vers un document.  
  
##  <a name="a-nameapplyprintdevicea--coledocumentapplyprintdevice"></a><a name="applyprintdevice"></a>COleDocument::ApplyPrintDevice  
 Appelez cette fonction pour modifier le périphérique cible à l’impression de tous les incorporé [COleClientItem](../../mfc/reference/coleclientitem-class.md) éléments dans le document de votre application conteneur.  
  
```  
BOOL ApplyPrintDevice(const DVTARGETDEVICE* ptd);  
BOOL ApplyPrintDevice(const PRINTDLG* ppd);
```  
  
### <a name="parameters"></a>Paramètres  
 `ptd`  
 Pointeur vers un **DVTARGETDEVICE** structure de données qui contient des informations sur le nouveau périphérique d’impression cible. Peut être **NULL**.  
  
 `ppd`  
 Pointeur vers un **PRINTDLG** structure de données qui contient des informations sur le nouveau périphérique d’impression cible. Peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction met à jour le périphérique d’impression pour tous les éléments, mais elle n’actualise pas le cache de présentation de ces éléments. Pour mettre à jour le cache de présentation pour un élément, appelez [COleClientItem::UpdateLink](../../mfc/reference/coleclientitem-class.md#updatelink).  
  
 Les arguments de cette fonction contiennent des informations OLE utilise pour identifier le périphérique cible. Le [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) structure contient des informations que Windows utilise pour initialiser la boîte de dialogue d’impression. Une fois que l’utilisateur ferme la boîte de dialogue, Windows renvoie des informations sur les sélections d’utilisateur dans cette structure. Le `m_pd` membre d’un [CPrintDialog](../../mfc/reference/cprintdialog-class.md) objet est un **PRINTDLG** structure.  
  
 Pour plus d’informations, consultez la [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations, consultez la [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecoledocumenta--coledocumentcoledocument"></a><a name="coledocument"></a>COleDocument::COleDocument  
 Construit un objet `COleDocument`.  
  
```  
COleDocument();
```  
  
##  <a name="a-nameenablecompoundfilea--coledocumentenablecompoundfile"></a><a name="enablecompoundfile"></a>COleDocument::EnableCompoundFile  
 Appelez cette fonction si vous souhaitez stocker le document en utilisant le format de fichier composé.  
  
```  
void EnableCompoundFile(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bEnable`  
 Spécifie si la prise en charge des fichiers composés est activé ou désactivé.  
  
### <a name="remarks"></a>Remarques  
 Cela est également appelée stockage structuré. Vous appelez généralement cette fonction à partir du constructeur de votre `COleDocument`-classe dérivée. Pour plus d’informations sur les documents composés, consultez l’article [conteneurs : fichiers composés](../../mfc/containers-compound-files.md)...  
  
 Si vous n’appelez pas cette fonction membre, les documents sont stockés dans un format non structuré (« plat »).  
  
 Une fois que la prise en charge des fichiers composés est activée ou désactivée pour un document, le paramètre ne doit pas être modifié pendant la durée de vie du document.  
  
##  <a name="a-namegetinplaceactiveitema--coledocumentgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>COleDocument::GetInPlaceActiveItem  
 Appel de cette fonction pour obtenir le OLE d’élément qui est actuellement activé sur place dans la fenêtre frame contenant la vue identifiée par `pWnd`.  
  
```  
virtual COleClientItem* GetInPlaceActiveItem(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pWnd`  
 Pointeur vers la fenêtre qui affiche le document conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’unique et place active élément OLE ; **NULL** s’il n’existe aucun élément OLE actuellement dans l’état « actif sur place ».  
  
##  <a name="a-namegetnextclientitema--coledocumentgetnextclientitem"></a><a name="getnextclientitem"></a>COleDocument::GetNextClientItem  
 Appelez cette fonction à plusieurs reprises pour accéder à chaque élément client dans votre document.  
  
```  
COleClientItem* GetNextClientItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Une référence à un **POSITION** par un appel précédent à valeur `GetNextClientItem`; la valeur initiale est retournée par la `GetStartPosition` fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément suivant de client dans le document, ou **NULL** si aucun élément n’est plus client.  
  
### <a name="remarks"></a>Remarques  
 Après chaque appel, la valeur de `pos` est définie pour l’élément suivant dans le document, ce qui peut ou ne peut pas un élément client.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCOleContainer n °&1;](../../mfc/codesnippet/cpp/coledocument-class_1.cpp)]  
  
##  <a name="a-namegetnextitema--coledocumentgetnextitem"></a><a name="getnextitem"></a>COleDocument::GetNextItem  
 Appelez cette fonction à plusieurs reprises pour accéder à chacun des éléments dans votre document.  
  
```  
virtual CDocItem* GetNextItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Une référence à un **POSITION** par un appel précédent à valeur `GetNextItem`; la valeur initiale est retournée par la `GetStartPosition` fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’élément de document à la position spécifiée.  
  
### <a name="remarks"></a>Notes  
 Après chaque appel, la valeur de `pos` est défini sur le **POSITION** la valeur de l’élément suivant dans le document. Si l’élément récupéré est le dernier élément dans le document, la nouvelle valeur de `pos` est **NULL**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCOleContainer n °&2;](../../mfc/codesnippet/cpp/coledocument-class_2.cpp)]  
  
##  <a name="a-namegetnextserveritema--coledocumentgetnextserveritem"></a><a name="getnextserveritem"></a>COleDocument::GetNextServerItem  
 Appelez cette fonction à plusieurs reprises pour accéder à chacun des éléments de serveur dans votre document.  
  
```  
COleServerItem* GetNextServerItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Une référence à un **POSITION** par un appel précédent à valeur `GetNextServerItem`; la valeur initiale est retournée par la `GetStartPosition` fonction membre.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément suivant de serveur dans le document, ou **NULL** si aucun élément n’est plus server.  
  
### <a name="remarks"></a>Remarques  
 Après chaque appel, la valeur de `pos` est définie pour l’élément suivant dans le document, ce qui peut ou ne peut pas un élément de serveur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCOleServer n °&2;](../../mfc/codesnippet/cpp/coledocument-class_3.cpp)]  
  
##  <a name="a-namegetprimaryselecteditema--coledocumentgetprimaryselecteditem"></a><a name="getprimaryselecteditem"></a>COleDocument::GetPrimarySelectedItem  
 Appelé par l’infrastructure pour récupérer l’élément OLE actuellement sélectionné dans la vue spécifiée.  
  
```  
virtual COleClientItem* GetPrimarySelectedItem(CView* pView);
```  
  
### <a name="parameters"></a>Paramètres  
 `pView`  
 Pointeur vers l’objet de vue active affichant le document.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers l’élément OLE sélectionné ; **NULL** si aucun élément OLE sélectionné ou si plusieurs est sélectionnée.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut recherche des éléments pour un seul élément sélectionné de la liste de relation contenant-contenu OLE et retourne un pointeur vers elle. Si aucun élément sélectionné, ou si plus d’un élément est sélectionné, la fonction retourne **NULL**. Vous devez substituer les `CView::IsSelected` fonction membre dans votre classe d’affichage pour cette fonction à utiliser. Remplacez cette fonction si vous avez votre propre méthode de stockage des éléments OLE.  
  
##  <a name="a-namegetstartpositiona--coledocumentgetstartposition"></a><a name="getstartposition"></a>COleDocument::GetStartPosition  
 Appelez cette fonction pour obtenir la position du premier élément dans le document.  
  
```  
virtual POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui peut être utilisée pour commencer à itérer au sein des éléments du document ; **NULL** si le document n’a pas d’éléments.  
  
### <a name="remarks"></a>Remarques  
 Passez la valeur retournée pour `GetNextItem`, `GetNextClientItem`, ou `GetNextServerItem`.  
  
##  <a name="a-namehasblankitemsa--coledocumenthasblankitems"></a><a name="hasblankitems"></a>COleDocument::HasBlankItems  
 Appelez cette fonction pour déterminer si le document contient des éléments vides.  
  
```  
BOOL HasBlankItems() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le document contient des éléments vides ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Est un élément vide dont le rectangle est vide.  
  
##  <a name="a-nameoneditchangeicona--coledocumentoneditchangeicon"></a><a name="oneditchangeicon"></a>COleDocument::OnEditChangeIcon  
 Affiche la boîte de dialogue OLE changer d’icône et modifie l’icône qui représente l’élément OLE actuellement sélectionné à l’icône que l’utilisateur sélectionne dans la boîte de dialogue.  
  
```  
afx_msg void OnEditChangeIcon();
```  
  
### <a name="remarks"></a>Remarques  
 `OnEditChangeIcon`Crée et lance un `COleChangeIconDialog` boîte de dialogue Changer d’icône.  
  
##  <a name="a-nameoneditconverta--coledocumentoneditconvert"></a><a name="oneditconvert"></a>COleDocument::OnEditConvert  
 Affiche la boîte de dialogue Convertir OLE et convertit ou Active l’élément OLE actuellement sélectionné en fonction des sélections de l’utilisateur dans la boîte de dialogue.  
  
```  
afx_msg void OnEditConvert();
```  
  
### <a name="remarks"></a>Notes  
 `OnEditConvert`Crée et lance un `COleConvertDialog` boîte de dialogue Convertir.  
  
 Un exemple de conversion convertit un document Microsoft Word dans un document WordPad.  
  
##  <a name="a-nameoneditlinksa--coledocumentoneditlinks"></a><a name="oneditlinks"></a>COleDocument::OnEditLinks  
 Affiche la boîte de dialogue OLE modifier/liens.  
  
```  
afx_msg void OnEditLinks();
```  
  
### <a name="remarks"></a>Remarques  
 `OnEditLinks`Crée et lance un `COleLinksDialog` boîte de dialogue liaisons qui permet aux utilisateurs de modifier les objets liés.  
  
##  <a name="a-nameonfilesendmaila--coledocumentonfilesendmail"></a><a name="onfilesendmail"></a>COleDocument::OnFileSendMail  
 Envoie un message via l’hôte de messagerie résident (le cas échéant) dans le document en tant que pièce jointe.  
  
```  
afx_msg void OnFileSendMail();
```  
  
### <a name="remarks"></a>Remarques  
 `OnFileSendMail`appels `OnSaveDocument` pour sérialiser (des documents sans titre et modifiés dans un fichier temporaire, qui est ensuite envoyé par courrier électronique Enregistrer). Si le document n’a pas été modifié, un fichier temporaire n’est pas nécessaire ; l’original est envoyé. `OnFileSendMail`charge MAPI32. DLL s’il n’a pas déjà été chargé.  
  
 Contrairement à l’implémentation de `OnFileSendMail` de **CDocument**, cette fonction gère correctement les fichiers composés.  
  
 Pour plus d’informations, consultez la [MAPI rubriques](../../mfc/mapi.md) et [prise en charge MAPI dans MFC](../../mfc/mapi-support-in-mfc.md) articles...  
  
##  <a name="a-nameonshowviewsa--coledocumentonshowviews"></a><a name="onshowviews"></a>COleDocument::OnShowViews  
 L’infrastructure appelle cette fonction après la visibilité du document modifications d’état.  
  
```  
virtual void OnShowViews(BOOL bVisible);
```  
  
### <a name="parameters"></a>Paramètres  
 `bVisible`  
 Indique si le document est devenu visible ou invisible.  
  
### <a name="remarks"></a>Notes  
 La version par défaut de cette fonction ne fait rien. Remplacer si votre application doit effectuer un traitement spécial lors de la visibilité du document change.  
  
##  <a name="a-nameonupdateeditchangeicona--coledocumentonupdateeditchangeicon"></a><a name="onupdateeditchangeicon"></a>COleDocument::OnUpdateEditChangeIcon  
 Appelé par l’infrastructure pour mettre à jour la commande Changer d’icône dans le menu Edition.  
  
```  
afx_msg void OnUpdateEditChangeIcon(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un `CCmdUI` structure qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la **activer** fonction membre de la `CCmdUI` par le biais de la structure `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
### <a name="remarks"></a>Remarques  
 `OnUpdateEditChangeIcon`interface d’utilisateur de la commande en fonction d’une icône valide existe ou non dans le document des mises à jour. Remplacez cette fonction pour modifier le comportement.  
  
##  <a name="a-nameonupdateeditlinksmenua--coledocumentonupdateeditlinksmenu"></a><a name="onupdateeditlinksmenu"></a>COleDocument::OnUpdateEditLinksMenu  
 Appelé par l’infrastructure pour mettre à jour la commande de liens dans le menu Edition.  
  
```  
afx_msg void OnUpdateEditLinksMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un `CCmdUI` structure qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la **activer** fonction membre de la `CCmdUI` par le biais de la structure `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
### <a name="remarks"></a>Notes  
 Commençant par le premier élément OLE dans le document, `OnUpdateEditLinksMenu` accède à chaque élément, vérifie si l’élément est un lien et s’il s’agit d’un lien, Active la commande de liens. Remplacez cette fonction pour modifier le comportement.  
  
##  <a name="a-nameonupdateobjectverbmenua--coledocumentonupdateobjectverbmenu"></a><a name="onupdateobjectverbmenu"></a>COleDocument::OnUpdateObjectVerbMenu  
 Appelé par l’infrastructure pour mettre à jour la *ObjectName* commande sur le menu Edition et le sous-menu verbe accédé à partir de la *ObjectName* commande, où *ObjectName* est le nom de l’objet OLE incorporé dans le document.  
  
```  
afx_msg void OnUpdateObjectVerbMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un `CCmdUI` structure qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la **activer** fonction membre de la `CCmdUI` par le biais de la structure `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
### <a name="remarks"></a>Notes  
 `OnUpdateObjectVerbMenu`mises à jour la *ObjectName* d’interface utilisateur de commandes en fonction d’un objet valide existe ou non dans le document. Si un objet existe, le *ObjectName* commande dans le menu Edition est activée. Lorsque cette option est sélectionnée, le sous-menu verbe s’affiche. Le sous-menu verbe contient toutes les commandes de verbe disponibles pour l’objet, telles que modifier, propriétés et ainsi de suite. Remplacez cette fonction pour modifier le comportement.  
  
##  <a name="a-nameonupdatepastelinkmenua--coledocumentonupdatepastelinkmenu"></a><a name="onupdatepastelinkmenu"></a>COleDocument::OnUpdatePasteLinkMenu  
 Appelé par l’infrastructure pour déterminer si un élément OLE lié peut être collé à partir du Presse-papiers.  
  
```  
afx_msg void OnUpdatePasteLinkMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un `CCmdUI` structure qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la **activer** fonction membre de la `CCmdUI` par le biais de la structure `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
### <a name="remarks"></a>Notes  
 La commande de menu Collage spécial est activée ou désactivée selon si l’élément peut être collé dans le document ou non.  
  
##  <a name="a-nameonupdatepastemenua--coledocumentonupdatepastemenu"></a><a name="onupdatepastemenu"></a>COleDocument::OnUpdatePasteMenu  
 Appelé par l’infrastructure pour déterminer si un élément OLE incorporé peut être collé à partir du Presse-papiers.  
  
```  
afx_msg void OnUpdatePasteMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>Paramètres  
 `pCmdUI`  
 Un pointeur vers un `CCmdUI` structure qui représente le menu qui a généré la commande de mise à jour. Appels du Gestionnaire de mise à jour la **activer** fonction membre de la `CCmdUI` par le biais de la structure `pCmdUI` pour mettre à jour l’interface utilisateur.  
  
### <a name="remarks"></a>Remarques  
 La commande de menu Coller et le bouton sont activées ou désactivées selon que l’élément peut être collé dans le document ou non.  
  
##  <a name="a-nameremoveitema--coledocumentremoveitem"></a><a name="removeitem"></a>COleDocument::RemoveItem  
 Appelez cette fonction pour supprimer un élément du document.  
  
```  
virtual void RemoveItem(CDocItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointeur vers l’élément de document à supprimer.  
  
### <a name="remarks"></a>Remarques  
 En règle générale, vous n’avez pas besoin d’appeler cette fonction explicitement ; elle est appelée par les destructeurs de `COleClientItem` et `COleServerItem`.  
  
##  <a name="a-nameupdatemodifiedflaga--coledocumentupdatemodifiedflag"></a><a name="updatemodifiedflag"></a>COleDocument::UpdateModifiedFlag  
 Appelez cette fonction pour indiquer que le document modifié si un des éléments OLE contenus ont été modifié.  
  
```  
virtual void UpdateModifiedFlag();
```  
  
### <a name="remarks"></a>Notes  
 Cela permet l’infrastructure inviter l’utilisateur à enregistrer le document avant de le fermer, même si les données natives dans le document n’a pas été modifiées.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC CONTAINER](../../visual-cpp-samples.md)   
 [Exemple MFC MFCBIND](../../visual-cpp-samples.md)   
 [CDocument (classe)](../../mfc/reference/cdocument-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




