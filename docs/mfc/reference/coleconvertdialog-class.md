---
title: Classe de la classe COleConvertDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleConvertDialog
- AFXODLGS/COleConvertDialog
- AFXODLGS/COleConvertDialog::COleConvertDialog
- AFXODLGS/COleConvertDialog::DoConvert
- AFXODLGS/COleConvertDialog::DoModal
- AFXODLGS/COleConvertDialog::GetClassID
- AFXODLGS/COleConvertDialog::GetDrawAspect
- AFXODLGS/COleConvertDialog::GetIconicMetafile
- AFXODLGS/COleConvertDialog::GetSelectionType
- AFXODLGS/COleConvertDialog::m_cv
dev_langs:
- C++
helpviewer_keywords:
- COleConvertDialog class
- OLE Convert dialog box
- dialog boxes, OLE
- OLE dialog boxes, Convert
- Convert dialog box
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6db5caf443e7f71c58e2c65b46794c2c9d246d38
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="coleconvertdialog-class"></a>Classe de la classe COleConvertDialog
Pour plus d’informations, consultez la [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleConvertDialog::COleConvertDialog](#coleconvertdialog)|Construit un objet `COleConvertDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleConvertDialog::DoConvert](#doconvert)|Effectue la conversion spécifiée dans la boîte de dialogue.|  
|[COleConvertDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE de modification d’élément.|  
|[COleConvertDialog::GetClassID](#getclassid)|Obtient le **CLSID** associé à l’élément sélectionné.|  
|[COleConvertDialog::GetDrawAspect](#getdrawaspect)|Spécifie s’il faut dessiner l’élément sous forme d’icône.|  
|[COleConvertDialog::GetIconicMetafile](#geticonicmetafile)|Obtient un handle de métafichier associé au formulaire sous forme d’icône de cet élément.|  
|[COleConvertDialog::GetSelectionType](#getselectiontype)|Obtient le type de sélection.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleConvertDialog::m_cv](#m_cv)|Structure qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Code de l’application conteneur généré par l’Assistant utilise cette classe.  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="coleconvertdialog"></a>COleConvertDialog::COleConvertDialog  
 Construit uniquement un `COleConvertDialog` objet.  
  
```  
explicit COleConvertDialog (
    COleClientItem* pItem,
    DWORD dwFlags = CF_SELECTCONVERTTO,
    CLSID* pClassID = NULL,
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointe vers l’élément à être converti ou activé.  
  
 `dwFlags`  
 Indicateur de création, qui contient un nombre quelconque des valeurs suivantes associées à l’aide de l’opérateur de bits- ou un opérateur :  
  
- **CF_SELECTCONVERTTO** Spécifie que la case d’option Convertir en sera sélectionnée initialement lorsque la boîte de dialogue est appelée. Il s'agit de la valeur par défaut.  
  
- **CF_SELECTACTIVATEAS** Spécifie que la case Activer en tant qu’est sélectionnée initialement lorsque la boîte de dialogue est appelée.  
  
- **CF_SETCONVERTDEFAULT** Spécifie que la classe dont **CLSID** est spécifié par le **clsidConvertDefault** membre de la `m_cv` structure sera utilisée comme la sélection par défaut dans la zone de liste de la classe lors de la convertir en case.  
  
- **CF_SETACTIVATEDEFAULT** Spécifie que la classe dont **CLSID** est spécifié par le **clsidActivateDefault** membre de la `m_cv` structure sera utilisée comme la sélection par défaut dans la zone de liste de la classe lorsque la case Activer en tant qu’est sélectionnée.  
  
- **CF_SHOWHELPBUTTON** Spécifie que le bouton aide s’affichera lorsque la boîte de dialogue est appelée.  
  
 `pClassID`  
 Pointe vers le CLSID de l’élément à être converti ou activé. Si **NULL**, le **CLSID** associés `pItem` sera utilisé.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) et [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) structure.  
  
##  <a name="doconvert"></a>COleConvertDialog::DoConvert  
 Appelez cette fonction, après le retour avec succès à partir de [DoModal](#domodal), soit pour convertir ou activer un objet de type [COleClientItem](../../mfc/reference/coleclientitem-class.md).  
  
```  
BOOL DoConvert(COleClientItem* pItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `pItem`  
 Pointe vers l’élément à être converti ou activé. Ne peut pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 L’élément est converti ou activé en fonction des données sélectionnées par l’utilisateur dans la boîte de dialogue Convertir.  
  
##  <a name="domodal"></a>COleConvertDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue Convertir OLE.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIConvert](http://msdn.microsoft.com/library/windows/desktop/ms680694) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_cv](#m_cv) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez appeler des fonctions pour récupérer les paramètres ou les informations qui a été entrées par l’utilisateur dans la boîte de dialogue autres membres.  
  
##  <a name="getclassid"></a>COleConvertDialog::GetClassID  
 Appelez cette fonction pour obtenir le **CLSID** l’élément associé à l’utilisateur sélectionné dans la boîte de dialogue Convertir.  
  
```  
REFCLSID GetClassID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le **CLSID** associé à l’élément qui a été sélectionné dans la boîte de dialogue Convertir.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
 Pour plus d’informations, consultez [clé CLSID](http://msdn.microsoft.com/library/windows/desktop/ms691424) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdrawaspect"></a>COleConvertDialog::GetDrawAspect  
 Appelez cette fonction pour déterminer si l’utilisateur a choisi d’afficher l’élément sélectionné en tant qu’icône.  
  
```  
DVASPECT GetDrawAspect() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La méthode nécessaire pour restituer l’objet.  
  
- `DVASPECT_CONTENT`Retourné si la case à cocher Afficher comme icône n’a pas été activée.  
  
- `DVASPECT_ICON`Retourné si la case à cocher Afficher comme icône a été vérifiée.  
  
### <a name="remarks"></a>Remarques  
 Appel de cette fonction uniquement après avoir [DoModal](#domodal) retourne **IDOK**.  
  
 Pour plus d’informations sur les aspects de dessin, consultez la [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) la structure de données dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="geticonicmetafile"></a>COleConvertDialog::GetIconicMetafile  
 Appelez cette fonction pour obtenir un handle de métafichier qui contient l’aspect de l’élément sélectionné sous forme d’icône.  
  
```  
HGLOBAL GetIconicMetafile() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle du métafichier contenant l’aspect sous forme d’icône de l’élément sélectionné, si la case à cocher Afficher comme icône est activée lorsque la boîte de dialogue a été fermée en choisissant **OK**; sinon **NULL**.  
  
##  <a name="getselectiontype"></a>COleConvertDialog::GetSelectionType  
 Appelez cette fonction pour déterminer le type de conversion sélectionnée dans la boîte de dialogue Convertir.  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Type de sélection.  
  
### <a name="remarks"></a>Notes  
 Les valeurs de type de retour sont spécifiés par le **sélection** type énumération déclarée dans la `COleConvertDialog` classe.  
  
```  
enum Selection {
    noConversion,
    convertItem,
    activateAs
    };  
```  
  
 Suivent de brèves descriptions de ces valeurs :  
  
- **COleConvertDialog::noConversion** retournée si la boîte de dialogue a été annulée ou que l’utilisateur a sélectionné aucune conversion. Si `COleConvertDialog::DoModal` retourné **IDOK**, il est possible que l’utilisateur a sélectionné une icône différente de celle précédemment sélectionnée.  
  
- **COleConvertDialog::convertItem** retournée si la case d’option Convertir en était activée, l’utilisateur a sélectionné un autre élément à convertir, et `DoModal` retourné **IDOK**.  
  
- **COleConvertDialog::activateAs** retournée si la case Activer en tant qu’a été activée, l’utilisateur a sélectionné un élément différent pour l’activer, et `DoModal` retourné **IDOK**.  
  
##  <a name="m_cv"></a>COleConvertDialog::m_cv  
 Structure de type **OLEUICONVERT** utilisé pour contrôler le comportement de la boîte de dialogue Convertir.  
  
```  
OLEUICONVERT m_cv;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

