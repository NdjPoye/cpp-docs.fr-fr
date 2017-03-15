---
title: Classe de la classe COlePasteSpecialDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePasteSpecialDialog
dev_langs:
- C++
helpviewer_keywords:
- Paste Special dialog box
- dialog boxes, Paste Special
- OLE Paste Special dialog box
- COlePasteSpecialDialog class
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
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
ms.openlocfilehash: 6984d714248815b062c564c7eed5c315990855af
ms.lasthandoff: 02/24/2017

---
# <a name="colepastespecialdialog-class"></a>Classe de la classe COlePasteSpecialDialog
Utilisée pour la boîte de dialogue OLE Collage spécial.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COlePasteSpecialDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](#colepastespecialdialog)|Construit un objet `COlePasteSpecialDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::AddFormat](#addformat)|Ajoute des formats personnalisés à la liste des formats de que votre application peut coller.|  
|[COlePasteSpecialDialog::AddLinkEntry](#addlinkentry)|Ajoute une nouvelle entrée à la liste des formats de Presse-papiers pris en charge.|  
|[COlePasteSpecialDialog::AddStandardFormats](#addstandardformats)|Ajoute **CF_BITMAP**, **CF_DIB**, `CF_METAFILEPICT`et éventuellement `CF_LINKSOURCE` à la liste des formats de votre application peut coller.|  
|[COlePasteSpecialDialog::CreateItem](#createitem)|Crée l’élément dans le document conteneur à l’aide du format spécifié.|  
|[COlePasteSpecialDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE Collage spécial.|  
|[COlePasteSpecialDialog::GetDrawAspect](#getdrawaspect)|Indique s’il faut dessiner élément sous forme d’icône ou non.|  
|[COlePasteSpecialDialog::GetIconicMetafile](#geticonicmetafile)|Obtient un handle de métafichier associé au formulaire sous forme d’icône de cet élément.|  
|[COlePasteSpecialDialog::GetPasteIndex](#getpasteindex)|Obtient l’index d’options de collage disponibles qui a été choisi par l’utilisateur.|  
|[COlePasteSpecialDialog::GetSelectionType](#getselectiontype)|Obtient le type de sélection.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePasteSpecialDialog::m_ps](#m_ps)|Une structure de type **OLEUIPASTESPECIAL** qui contrôle la fonction de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 Créer un objet de classe `COlePasteSpecialDialog` lorsque vous souhaitez appeler cette boîte de dialogue. Après un `COlePasteSpecialDialog` objet a été construit, vous pouvez utiliser la [AddFormat](#addformat) et [AddStandardFormats](#addstandardformats) des fonctions membres pour ajouter des formats de Presse-papiers à la boîte de dialogue. Vous pouvez également utiliser le [m_ps](#m_ps) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_ps` structure est de type **OLEUIPASTESPECIAL**.  
  
 Pour plus d’informations, consultez la [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-nameaddformata--colepastespecialdialogaddformat"></a><a name="addformat"></a>COlePasteSpecialDialog::AddFormat  
 Appelez cette fonction pour ajouter de nouveaux formats à la liste des formats de que votre application peut prendre en charge dans une opération de collage spécial.  
  
```  
void AddFormat(
    const FORMATETC& formatEtc,  
    LPTSTR lpszFormat,  
    LPTSTR lpszResult,  
    DWORD flags);

 
void AddFormat(
    UINT cf,  
    DWORD tymed,  
    UINT nFormatID,  
    BOOL bEnableIcon,  
    BOOL bLink);
```  
  
### <a name="parameters"></a>Paramètres  
 *utilise*  
 Référence au type de données à ajouter.  
  
 `lpszFormat`  
 Chaîne qui décrit le format à l’utilisateur.  
  
 *lpszResult*  
 Chaîne qui décrit le résultat si ce format est choisi dans la boîte de dialogue.  
  
 `flags`  
 L’autre liaison et incorporation options disponibles pour ce format. Cet indicateur est une combinaison d’un ou plusieurs des valeurs différentes dans les **OLEUIPASTEFLAG** type énuméré.  
  
 `cf`  
 Le format du Presse-papiers à ajouter.  
  
 *TYMED*  
 Les types de supports disponibles dans ce format. Il s’agit d’une combinaison de bits d’une ou plusieurs des valeurs dans le **TYMED** type énuméré.  
  
 `nFormatID`  
 ID de la chaîne qui identifie ce format. Le format de cette chaîne est de deux chaînes séparées par un caractère « \n ». La première chaîne est celle qui est passée dans le *lpstrFormat* paramètre et le second est le même que le *lpstrResult* paramètre.  
  
 *bEnableIcon*  
 Indicateur qui détermine si la case à cocher Afficher sous forme d’icône est activée quand ce format est choisi dans la zone de liste.  
  
 *bLink*  
 Indicateur qui détermine si la case d’option Coller la liaison est activée quand ce format est choisi dans la zone de liste.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction peut être appelée pour ajouter deux formats standard tels que **CF_TEXT** ou **CF_TIFF** ou des formats personnalisés pour votre application est enregistrée avec le système. Pour plus d’informations sur le collage d’objets de données dans votre application, consultez l’article [des objets de données et Sources de données : Manipulation](../../mfc/data-objects-and-data-sources-manipulation.md).  
  
 Pour plus d’informations, consultez la [TYMED](http://msdn.microsoft.com/library/windows/desktop/ms691227) type d’énumération et la [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations, consultez la [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) énumérée de type dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameaddlinkentrya--colepastespecialdialogaddlinkentry"></a><a name="addlinkentry"></a>COlePasteSpecialDialog::AddLinkEntry  
 Ajoute une nouvelle entrée à la liste des formats de Presse-papiers pris en charge.  
  
```  
OLEUIPASTEFLAG AddLinkEntry(UINT cf);
```  
  
### <a name="parameters"></a>Paramètres  
 `cf`  
 Le format du Presse-papiers à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Un [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) structure contenant les informations de la nouvelle entrée de lien.  
  
##  <a name="a-nameaddstandardformatsa--colepastespecialdialogaddstandardformats"></a><a name="addstandardformats"></a>COlePasteSpecialDialog::AddStandardFormats  
 Appelez cette fonction pour ajouter les formats de Presse-papiers suivants à la liste des formats de que votre application peut prendre en charge dans une opération de collage spécial :  
  
```  
void AddStandardFormats(BOOL bEnableLink = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *bEnableLink*  
 Indicateur qui détermine s’il faut ajouter `CF_LINKSOURCE` à la liste des formats de votre application peut coller.  
  
### <a name="remarks"></a>Notes  
  
- **CF_BITMAP**  
  
- **CF_DIB**  
  
- `CF_METAFILEPICT`  
  
- **Objet « incorporé »**  
  
-   (facultatif) **« Liaison »**  
  
 Ces formats sont utilisés pour prendre en charge l’incorporation et la liaison.  
  
##  <a name="a-namecolepastespecialdialoga--colepastespecialdialogcolepastespecialdialog"></a><a name="colepastespecialdialog"></a>COlePasteSpecialDialog::COlePasteSpecialDialog  
 Construit un objet `COlePasteSpecialDialog`.  
  
```  
COlePasteSpecialDialog(
    DWORD dwFlags = PSF_SELECTPASTE,  
    COleDataObject* pDataObject = NULL,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Indicateur de création, contient un ou plusieurs indicateurs suivants associés à l’aide de l’opérateur de bits OR :  
  
- `PSF_SELECTPASTE`Spécifie que la case d’option Coller sera vérifiée initialement lorsque la boîte de dialogue est appelée. Ne peut pas être utilisé en association avec `PSF_SELECTPASTELINK`. Il s'agit de la valeur par défaut.  
  
- `PSF_SELECTPASTELINK`Spécifie que le lien coller case sera activée initialement lorsque la boîte de dialogue est appelée. Ne peut pas être utilisé en association avec `PSF_SELECTPASTE`.  
  
- `PSF_CHECKDISPLAYASICON`Spécifie que la case à cocher Afficher comme icône seront vérifié initialement lorsque la boîte de dialogue est appelée.  
  
- `PSF_SHOWHELP`Spécifie que le bouton aide s’affichera lorsque la boîte de dialogue est appelée.  
  
 `pDataObject`  
 Pointe vers le [COleDataObject](../../mfc/reference/coledataobject-class.md) de collage. Si cette valeur est **NULL**, il obtient le `COleDataObject` à partir du Presse-papiers.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction crée uniquement une `COlePasteSpecialDialog` objet. Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
 Pour plus d’informations, consultez la [OLEUIPASTEFLAG](http://msdn.microsoft.com/library/windows/desktop/ms682172) énumérée de type dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecreateitema--colepastespecialdialogcreateitem"></a><a name="createitem"></a>COlePasteSpecialDialog::CreateItem  
 Crée le nouvel élément a été choisi dans la boîte de dialogue Collage spécial.  
  
```  
BOOL CreateItem(COleClientItem* pNewItem);
```  
  
### <a name="parameters"></a>Paramètres  
 *pNewItem*  
 Pointe vers une `COleClientItem` instance. Ne peut pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’élément a été créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction doit être appelée uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
##  <a name="a-namedomodala--colepastespecialdialogdomodal"></a><a name="domodal"></a>COlePasteSpecialDialog::DoModal  
 Affiche la boîte de dialogue OLE Collage spécial.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le `COleDialog::GetLastError` fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIPasteSpecial](http://msdn.microsoft.com/library/windows/desktop/ms694512) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_ps](#m_ps) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez appeler des fonctions à récupérer les paramètres ou les informations saisies par l’utilisateur dans la boîte de dialogue autres membres.  
  
##  <a name="a-namegetdrawaspecta--colepastespecialdialoggetdrawaspect"></a><a name="getdrawaspect"></a>COlePasteSpecialDialog::GetDrawAspect  
 Détermine si l’utilisateur a choisi d’afficher l’élément sélectionné en tant qu’icône.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La méthode nécessaire pour restituer l’objet.  
  
- `DVASPECT_CONTENT`Retourné si la case à cocher Afficher comme icône n’était pas vérifiée lors du rejet de la boîte de dialogue.  
  
- `DVASPECT_ICON`Retourné si la case à cocher Afficher comme icône a été vérifiée lorsque la boîte de dialogue a été fermée.  
  
### <a name="remarks"></a>Notes  
 Appelez uniquement cette fonction après [DoModal](#domodal) retourne **IDOK**.  
  
 Pour plus d’informations sur les aspects de dessin, consultez la [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegeticonicmetafilea--colepastespecialdialoggeticonicmetafile"></a><a name="geticonicmetafile"></a>COlePasteSpecialDialog::GetIconicMetafile  
 Obtient le métafichier associé à l’élément sélectionné par l’utilisateur.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle du métafichier contenant l’aspect sous forme d’icône de l’élément sélectionné, si la case à cocher Afficher comme icône a été sélectionné lors du rejet de la boîte de dialogue en choisissant **OK**; sinon **NULL**.  
  
##  <a name="a-namegetpasteindexa--colepastespecialdialoggetpasteindex"></a><a name="getpasteindex"></a>COlePasteSpecialDialog::GetPasteIndex  
 Obtient la valeur d’index associé à l’entrée sélectionnée par l’utilisateur.  
  
```  
int GetPasteIndex() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’index dans le tableau de **OLEUIPASTEENTRY** des structures qui a été sélectionnée par l’utilisateur. Le format qui correspond à l’index sélectionné doit être utilisé lors de l’exécution de l’opération de collage.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez la [OLEUIPASTEENTRY](http://msdn.microsoft.com/library/windows/desktop/ms690165) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetselectiontypea--colepastespecialdialoggetselectiontype"></a><a name="getselectiontype"></a>COlePasteSpecialDialog::GetSelectionType  
 Détermine le type de sélection de l’utilisateur.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le type de sélection.  
  
### <a name="remarks"></a>Remarques  
 Les valeurs de type de retour sont spécifiés par le **sélection** type énumération déclarée dans la `COlePasteSpecialDialog` classe.  
  
 `enum Selection`  
  
 `{`  
  
 `pasteLink,`  
  
 `pasteNormal,`  
  
 `pasteOther,`  
  
 `pasteStatic`  
  
 `};`  
  
 Procédez de la brève desccriptions des valeurs suivantes :  
  
- **COlePasteSpecialDialog::pasteLink** case Coller avec la liaison a été vérifiée et le format choisi a un format OLE standard.  
  
- **COlePasteSpecialDialog::pasteNormal** case le collage a été vérifiée et le format choisi a un format OLE standard.  
  
- **COlePasteSpecialDialog::pasteOther** le format sélectionné n’est pas un format OLE standard.  
  
- **COlePasteSpecialDialog::pasteStatic** le format choisi a été un métafichier.  
  
##  <a name="a-namempsa--colepastespecialdialogmps"></a><a name="m_ps"></a>COlePasteSpecialDialog::m_ps  
 Structure de type **OLEUIPASTESPECIAL** utilisé pour contrôler le comportement de la boîte de dialogue Collage spécial.  
  
```  
OLEUIPASTESPECIAL m_ps;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

