---
title: Classe de CFolderPickerDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog class
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
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
ms.openlocfilehash: 0d020544a16056d3f4db538750ed5a16b54f9a51
ms.lasthandoff: 02/24/2017

---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog, classe
CFolderPickerDialog classe implémente CFileDialog en mode de sélecteur de dossier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFolderPickerDialog : public CFileDialog;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFolderPickerDialog :: ~ CFolderPickerDialog](#cfolderpickerdialog__~cfolderpickerdialog)|Destructeur.|  
|[CFolderPickerDialog::CFolderPickerDialog](#cfolderpickerdialog)|Constructeur.|  
  
## <a name="remarks"></a>Remarques  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
 `CFolderPickerDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="cfolderpickerdialog"></a>CFolderPickerDialog::CFolderPickerDialog  
 Constructeur.  
  
```  
explicit CFolderPickerDialog(
    LPCTSTR lpszFolder = NULL,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFolder`  
 Dossier initial.  
  
 `dwFlags`  
 Une combinaison d’un ou plusieurs indicateurs qui vous permettent de personnaliser la boîte de dialogue.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de l’objet de boîte de dialogue.  
  
 `dwSize`  
 La taille de la structure OPENFILENAME.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="_dtorcfolderpickerdialog"></a>CFolderPickerDialog :: ~ CFolderPickerDialog  
 Destructeur.  
  
```  
virtual ~CFolderPickerDialog();
```  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

