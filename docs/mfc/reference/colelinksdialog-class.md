---
title: Classe de COleLinksDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleLinksDialog
dev_langs:
- C++
helpviewer_keywords:
- Edit Links dialog box
- COleLinksDialog class
- dialog boxes, OLE
- OLE Edit Links dialog box
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
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
ms.openlocfilehash: ed256b3a4d3236863e3dcccb7614949f650f058b
ms.lasthandoff: 02/24/2017

---
# <a name="colelinksdialog-class"></a>COleLinksDialog (classe)
Utilisée pour la boîte de dialogue OLE Modifier les liens.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleLinksDialog::COleLinksDialog](#colelinksdialog)|Construit un objet `COleLinksDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleLinksDialog::DoModal](#domodal)|Affiche la boîte de dialogue OLE modifier les liens.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleLinksDialog::m_el](#m_el)|Une structure de type **OLEUIEDITLINKS** qui contrôle le comportement de la boîte de dialogue.|  
  
## <a name="remarks"></a>Remarques  
 Créer un objet de classe `COleLinksDialog` lorsque vous souhaitez appeler cette boîte de dialogue. Après un `COleLinksDialog` objet a été construit, vous pouvez utiliser la [m_el](#m_el) structure pour initialiser les valeurs ou les États des contrôles dans la boîte de dialogue. Le `m_el` structure est de type **OLEUIEDITLINKS**. Pour plus d’informations sur l’utilisation de cette classe de boîte de dialogue, consultez la [DoModal](#domodal) fonction membre.  
  
> [!NOTE]
>  Code de l’application conteneur généré par l’Assistant utilise cette classe.  
  
 Pour plus d’informations, consultez la [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur les boîtes de dialogue spécifiques à OLE, consultez l’article [des boîtes de dialogue OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxodlgs.h  
  
##  <a name="a-namedomodala--colelinksdialogdomodal"></a><a name="domodal"></a>COleLinksDialog::DoModal  
 Affiche la boîte de dialogue OLE modifier les liens.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 État d’achèvement de la boîte de dialogue. Une des valeurs suivantes :  
  
- **IDOK** si la boîte de dialogue est affichée avec succès.  
  
- **IDCANCEL** si l’utilisateur a annulé la boîte de dialogue.  
  
- **IDABORT** si une erreur s’est produite. Si **IDABORT** est retourné, appelez le `COleDialog::GetLastError` fonction membre pour obtenir plus d’informations sur le type d’erreur qui s’est produite. Pour obtenir la liste des erreurs possibles, consultez la [OleUIEditLinks](http://msdn.microsoft.com/library/windows/desktop/ms679703) de fonction dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Remarques  
 Si vous souhaitez initialiser les différents contrôles de boîte de dialogue en définissant les membres de la [m_el](#m_el) structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
##  <a name="a-namecolelinksdialoga--colelinksdialogcolelinksdialog"></a><a name="colelinksdialog"></a>COleLinksDialog::COleLinksDialog  
 Construit un objet `COleLinksDialog`.  
  
```  
COleLinksDialog (
    COleDocument* pDoc,  
    CView* pView,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDoc`  
 Pointe vers le document OLE qui contient les liens à modifier.  
  
 `pView`  
 Pointe vers la vue actuelle sur `pDoc`.  
  
 `dwFlags`  
 Indicateur de création, qui contient 0 ou **ELF_SHOWHELP** pour spécifier si le bouton aide s’affichera lorsque la boîte de dialogue s’affiche.  
  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type `CWnd`) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la fenêtre parente de la boîte de dialogue est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Notes  
 Cette fonction crée uniquement une `COleLinksDialog` objet. Pour afficher la boîte de dialogue, appelez le [DoModal](#domodal) (fonction).  
  
##  <a name="a-namemela--colelinksdialogmel"></a><a name="m_el"></a>COleLinksDialog::m_el  
 Structure de type **OLEUIEDITLINKS** utilisé pour contrôler le comportement de la boîte de dialogue Modifier les liaisons.  
  
```  
OLEUIEDITLINKS m_el;  
```  
  
### <a name="remarks"></a>Remarques  
 Les membres de cette structure peuvent être modifiés directement ou via les fonctions membres.  
  
 Pour plus d’informations, consultez la [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

