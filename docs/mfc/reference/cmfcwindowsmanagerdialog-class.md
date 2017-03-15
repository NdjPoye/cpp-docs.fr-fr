---
title: Classe de CMFCWindowsManagerDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog class
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
caps.latest.revision: 25
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
ms.openlocfilehash: 9f1508cfd3844fed413edd69063f1b3e64e80195
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog (classe)
Le `CMFCWindowsManagerDialog` objet permet à un utilisateur de gérer les fenêtres enfants MDI dans une application MDI.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|Construit un objet `CMFCWindowsManagerDialog`.|  
  
## <a name="remarks"></a>Notes  
 La `CMFCWindowsManagerDialog` contient une liste des fenêtres enfants MDI qui sont actuellement ouverts dans l’application. L’utilisateur peut contrôler manuellement l’état des fenêtres MDI enfants à l’aide de cette boîte de dialogue.  
  
 `CMFCWindowsManagerDialog`est incorporé dans le [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md). Le `CMFCWindowsManagerDialog` n’est pas une classe que vous devez créer manuellement. Au lieu de cela, appelez la fonction [CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog), et il crée et affiche un `CMFCWindowsManagerDialog` objet.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment construire un `CMFCWindowsManagerDialog` objet en appelant `CMDIFrameWndEx::ShowWindowsDialog`. Cet extrait de code fait partie de la [exemple de Visual Studio démonstration](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#18;](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxWindowsManagerDialog.h  
  
##  <a name="a-namecmfcwindowsmanagerdialoga--cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a>CMFCWindowsManagerDialog::CMFCWindowsManagerDialog  
 Construit un [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) objet.  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMDIFrame`  
 Pointeur vers la fenêtre parente ou propriétaire.  
  
 [in] `bHelpButton`  
 Un paramètre booléen qui indique si le framework affiche un **aide** bouton.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur les gestionnaires visuels, consultez [Gestionnaire de visualisation](../../mfc/visualization-manager.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx Class](../../mfc/reference/cmdiframewndex-class.md)

