---
title: Classe de CCommonDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], Windows common dialogs
- common dialog boxes [C++], common dialog classes
- common dialog classes [C++]
- MFC dialog boxes, Windows common dialogs
- Windows common dialogs [C++]
- CCommonDialog class
- dialog classes [C++], common
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
caps.latest.revision: 20
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
ms.openlocfilehash: 93d4cd4ca794095c225641bc67353b9a53080c3c
ms.lasthandoff: 02/24/2017

---
# <a name="ccommondialog-class"></a>CCommonDialog (classe)
Classe de base pour les classes qui encapsulent les fonctionnalités des boîtes de dialogue communes Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|Construit un objet `CCommonDialog`.|  
  
## <a name="remarks"></a>Remarques  
 Les classes suivantes encapsulent la fonctionnalité des boîtes de dialogue communes Windows :  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="ccommondialog"></a>CCommonDialog::CCommonDialog  
 Construit un objet `CCommonDialog`.  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointe vers l’objet de fenêtre parente ou propriétaire (de type [CWnd](../../mfc/reference/cwnd-class.md)) auquel appartient l’objet de la boîte de dialogue. S’il s’agit **NULL**, la boîte de dialogue fenêtre l’objet parent est définie dans la fenêtre principale de l’application.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [CDialog::CDialog](../../mfc/reference/cdialog-class.md#cdialog) pour obtenir des informations complètes.  
  
## <a name="see-also"></a>Voir aussi  
 [CDialog (classe)](../../mfc/reference/cdialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFileDialog (classe)](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog (classe)](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog (classe)](../../mfc/reference/ccolordialog-class.md)   
 [CPageSetupDialog (classe)](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog (classe)](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog (classe)](../../mfc/reference/cfindreplacedialog-class.md)   
 [COleDialog (classe)](../../mfc/reference/coledialog-class.md)

