---
title: Classe de la classe COleInsertDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleInsertDialog
dev_langs:
- C++
helpviewer_keywords:
- OLE Insert Object dialog box
- dialog boxes, OLE
- COleInsertDialog class
- Insert Object dialog box
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
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
ms.openlocfilehash: 078f421dacc79ff929249cd35c520b0c4d4a222e
ms.lasthandoff: 02/24/2017

---
# <a name="coleinsertdialog-class"></a>Classe de la classe COleInsertDialog
Utilisée pour la boîte de dialogue OLE Insérer un objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleInsertDialog::COleInsertDialog](#coleinsertdialog)|Construit un objet `COleInsertDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleInsertDialog::CreateItem](#createitem)|Crée l’élément sélectionné dans la boîte de dialogue.|  
|[COleInsertDialog::DoModal](#domodal)|Affiche la boîte de dialogue Insérer un objet OLE.|  
|[COleInsertDialog::GetClassID](#getclassid)|Obtient le **CLSID** associé à l’élément sélectionné.|  
|[COleInsertDialog::GetDrawAspect](#getdrawaspect)|Indique s’il faut dessiner l’élément sous forme d’icône.|  
|[COleInsertDialog::GetIconicMetafile](#geticonicmetafile)|Obtient un handle de métafichier associé au formulaire sous forme d’icône de cet élément.|  
|[COleInsertDialog::GetPathName](#getpathname)|Obtient le chemin d’accès complet au fichier sélectionné dans la boîte de dialogue.|  
|[COleInsertDialog::GetSelectionType](#getselectiontype)|Obtient le type d’objet sélectionné.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleInsertDialog::m_io](#m_io)|Une structure de type **OLEUIINSERTOBJECT** qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 Créer un objet de classe `COleInsertDialog` lorsque vous souhaitez appeler cette boîte de dialogue. Après un `COleInsertDialog` objet a été construit, vous pouvez utiliser la [m_io](#m_io) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_io` structure est de type **OLEUIINSERTOBJECT**. Pour plus d’informations sur l’utilisation de cette classe de boîte de dialogue, consultez la [DoModal](#domodal) fonction membre.  
  
> [!NOTE]
>  Code de l’application conteneur généré par l’Assistant utilise cette classe.  
  
 Pour plus d’informations, consultez la [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namecoleinsertdialoga--coleinsertdialogcoleinsertdialog"></a><a name="coleinsertdialog"></a>COleInsertDialog::COleInsertDialog  
 Cette fonction crée uniquement une `COleInsertDialog` objet.  
  
```  
COleInsertDialog (
    DWORD dwFlags = IOF_SELECTCREATENEW,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Indicateur de création qui contient un nombre quelconque des valeurs suivantes pour être combinées à l’aide de l’opérateur de bits OR :  
  
- **IOF_SHOWHELP** Spécifie que le bouton aide s’affichera lorsque la boîte de dialogue est appelée.  
  
- **IOF_SELECTCREATENEW** Spécifie que le nouveau bouton radio est sélectionné initialement lorsque la boîte de dialogue est appelée. Ceci est la valeur par défaut et ne peut pas être utilisé avec **IOF_SELECTCREATEFROMFILE**.  
  
- **IOF_SELECTCREATEFROMFILE** Spécifie que la case d’option Créer à partir du fichier sera sélectionnée initialement lorsque la boîte de dialogue est appelée. Ne peut pas être utilisé avec **IOF_SELECTCREATENEW**.  
  
- **IOF_CHECKLINK** indique que la case à cocher lien seront vérifié initialement lorsque la boîte de dialogue est appelée.  
  
- **IOF_DISABLELINK** Spécifie que la case à cocher lien va être désactivé lorsque la boîte de dialogue est appelée.  
  
- **IOF_CHECKDISPLAYASICON** Spécifie que la case à cocher Afficher comme icône sera être vérifié au départ, l’icône en cours s’affiche et le bouton Changer d’icône est activé lorsque la boîte de dialogue est appelée.  
  
- **IOF_VERIFYSERVERSEXIST** Spécifie que la boîte de dialogue doit valider les classes qu’il ajoute à la zone de liste en s’assurant que les serveurs spécifiés dans la base de registres existent avant que la boîte de dialogue s’affiche. Définition de cet indicateur peut nuire considérablement aux performances.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de l’objet de la boîte de dialogue est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Notes  
 Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
##  <a name="a-namecreateitema--coleinsertdialogcreateitem"></a><a name="createitem"></a>COleInsertDialog::CreateItem  
 Appelez cette fonction pour créer un objet de type [COleClientItem](../../mfc/reference/coleclientitem-class.md) uniquement si [DoModal](#domodal) retourne **IDOK**.  
  
```  
BOOL CreateItem(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointe vers l’élément à créer.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément a été créé ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Vous devez allouer la `COleClientItem` de l’objet avant d’appeler cette fonction.  
  
##  <a name="a-namedomodala--coleinsertdialogdomodal"></a><a name="domodal"></a>COleInsertDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue Insérer un objet OLE.  
  
```  
virtual INT_PTR   
    DoModal();

 
INT_PTR   
    DoModal(DWORD  dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Une des valeurs suivantes :  
  
 `COleInsertDialog::DocObjectsOnly`insère uniquement DocObjects.  
  
 `COleInsertDialog::ControlsOnly`insère uniquement des contrôles ActiveX.  
  
 Zéro insère un contrôle ActiveX ni DocObject. Résultats de cette valeur dans la même implémentation que le premier prototype répertoriées ci-dessus.  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
-   IDOK si la boîte de dialogue est affichée avec succès.  
  
-   IDCANCEL, si l’utilisateur a annulé la boîte de dialogue.  
  
-   IDABORT si une erreur s’est produite. Si IDABORT est retourné, appelez le [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIInsertObject](http://msdn.microsoft.com/library/windows/desktop/ms694325) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_io](#m_io) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne IDOK, vous pouvez appeler des fonctions pour récupérer les paramètres ou les informations saisies dans la boîte de dialogue par l’utilisateur autres membres.  
  
##  <a name="a-namegetclassida--coleinsertdialoggetclassid"></a><a name="getclassid"></a>COleInsertDialog::GetClassID  
 Appelez cette fonction pour obtenir le **CLSID** associé à l’élément sélectionné uniquement si [DoModal](#domodal) retourne **IDOK** et le type de sélection est **COleInsertDialog::createNewItem**.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le **CLSID** associé à l’élément sélectionné.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdrawaspecta--coleinsertdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COleInsertDialog::GetDrawAspect  
 Appelez cette fonction pour déterminer si l’utilisateur a choisi d’afficher l’élément sélectionné en tant qu’icône.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La méthode nécessaire pour restituer l’objet.  
  
- `DVASPECT_CONTENT`Retourné si la case à cocher Afficher comme icône n’a pas été activée.  
  
- `DVASPECT_ICON`Retourné si la case à cocher Afficher comme icône a été vérifiée.  
  
### <a name="remarks"></a>Notes  
 Appelez cette ne fonctionnent que si [DoModal](#domodal) retourne **IDOK**.  
  
 Pour plus d’informations sur les aspects de dessin, consultez [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) la structure de données dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegeticonicmetafilea--coleinsertdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COleInsertDialog::GetIconicMetafile  
 Appelez cette fonction pour obtenir un handle de métafichier qui contient l’aspect de l’élément sélectionné sous forme d’icône.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle du métafichier contenant l’aspect sous forme d’icône de l’élément sélectionné, si la case à cocher Afficher comme icône est activée lorsque la boîte de dialogue a été fermée en choisissant **OK**; sinon **NULL**.  
  
##  <a name="a-namegetpathnamea--coleinsertdialoggetpathname"></a><a name="getpathname"></a>COleInsertDialog::GetPathName  
 Appelez cette fonction pour obtenir le chemin d’accès complet de la fichier sélectionné uniquement si [DoModal](#domodal) retourne **IDOK** et le type de sélection n’est pas **COleInsertDialog::createNewItem**.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le chemin d’accès complet au fichier sélectionné dans la boîte de dialogue. Si le type de sélection est `createNewItem`, cette fonction retourne un sans signification `CString` en mode version finale ou provoque une assertion en mode débogage.  
  
##  <a name="a-namegetselectiontypea--coleinsertdialoggetselectiontype"></a><a name="getselectiontype"></a>COleInsertDialog::GetSelectionType  
 Appelez cette fonction pour obtenir le type de sélection choisi lors du rejet de la boîte de dialogue Insérer un objet en choisissant **OK**.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Type de sélection.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de type de retour sont spécifiés par le **sélection** type énumération déclarée dans la `COleInsertDialog` classe.  
  
 `enum Selection`  
  
 `{`  
  
 `createNewItem,`  
  
 `insertFromFile,`  
  
 `linkToFile`  
  
 `};`  
  
 Suivent de brèves descriptions de ces valeurs :  
  
- **COleInsertDialog::createNewItem** créer le nouveau bouton radio a été sélectionné.  
  
- **COleInsertDialog::insertFromFile** case le créer à partir du fichier a été sélectionné et la case à cocher lien n’a pas été activée.  
  
- **COleInsertDialog::linkToFile** case le créer à partir du fichier a été sélectionné et la case à cocher lien a été activée.  
  
##  <a name="a-namemioa--coleinsertdialogmio"></a><a name="m_io"></a>COleInsertDialog::m_io  
 Structure de type **OLEUIINSERTOBJECT** utilisé pour contrôler le comportement de la boîte de dialogue Insérer un objet.  
  
```  
OLEUIINSERTOBJECT m_io;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

