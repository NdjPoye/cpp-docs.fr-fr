---
title: Cfolderpickerdialog, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog
- AFXDLGS/CFolderPickerDialog::CFolderPickerDialog
dev_langs:
- C++
helpviewer_keywords:
- CFolderPickerDialog [MFC], CFolderPickerDialog
ms.assetid: 8db01684-dd1d-4e9c-989e-07a2318a8156
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 2ca0f618006345d0d36650655a4e62d721b4d4d4
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="cfolderpickerdialog-class"></a>CFolderPickerDialog, classe
Cfolderpickerdialog, classe implémente CFileDialog en mode de sélecteur de dossier.  
  
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
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
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
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

