---
title: Classe de COleUpdateDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleUpdateDialog
dev_langs:
- C++
helpviewer_keywords:
- Update dialog
- links [C++], updating
- updating OLE links
- OLE dialog boxes, Edit Link
- OLE link updating
- COleUpdateDialog class
ms.assetid: 699ca980-52b1-4cf8-9ab1-ac6767ad5b0e
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8066a8dc9e572c14e9423af62d340e249351ac11
ms.lasthandoff: 02/24/2017

---
# <a name="coleupdatedialog-class"></a>COleUpdateDialog (classe)
Utilisée pour un cas particulier de la boîte de dialogue OLE Modifier les liens, qui doit être utilisée lorsque vous devez mettre à jour uniquement les objets liés ou incorporés d'un document.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleUpdateDialog : public COleLinksDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleUpdateDialog::COleUpdateDialog](#coleupdatedialog)|Construit un objet `COleUpdateDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleUpdateDialog::DoModal](#domodal)|Affiche la **modifier les liens** boîte de dialogue dans un mode de mise à jour.|  
  
## <a name="remarks"></a>Remarques  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)  
  
 `COleUpdateDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namecoleupdatedialoga--coleupdatedialogcoleupdatedialog"></a><a name="coleupdatedialog"></a>COleUpdateDialog::COleUpdateDialog  
 Construit un objet `COleUpdateDialog`.  
  
```  
explicit COleUpdateDialog(
    COleDocument* pDoc,  
    BOOL bUpdateLinks = TRUE,  
    BOOL bUpdateEmbeddings = FALSE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDoc`  
 Pointe vers le document qui contient les liens qui peuvent nécessiter une mise à jour.  
  
 *bUpdateLinks*  
 Indicateur qui détermine si les objets liés sont à jour.  
  
 *bUpdateEmbeddings*  
 Indicateur qui détermine si des objets incorporés doivent être mis à jour.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue sera définie sur la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction crée uniquement une `COleUpdateDialog` objet. Pour afficher la boîte de dialogue, appelez [DoModal](../../mfc/reference/colelinksdialog-class.md#domodal). Cette classe doit être utilisée à la place de `COleLinksDialog` lorsque vous souhaitez mettre à jour uniquement les éléments liés ou incorporés.  
  
##  <a name="a-namedomodala--coleupdatedialogdomodal"></a><a name="domodal"></a>COleUpdateDialog::DoModal  
 Affiche la boîte de dialogue Modifier les liaisons zone mises à jour en mode.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue a été retourné avec succès.  
  
- **IDCANCEL** si aucun des éléments liés ou incorporés dans le document actif doivent mettre à jour.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le [COleDialog::GetLastError](../../mfc/reference/coledialog-class.md#getlasterror) fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Tous les liens et/ou des incorporations sont mis à jour, sauf si l’utilisateur sélectionne le bouton Annuler.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC OCLIENT](../../visual-cpp-samples.md)   
 [COleLinksDialog (classe)](../../mfc/reference/colelinksdialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleLinksDialog (classe)](../../mfc/reference/colelinksdialog-class.md)

