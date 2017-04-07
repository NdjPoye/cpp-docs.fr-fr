---
title: Classe de CMFCDesktopAlertDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::CreateFromParams
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::GetDlgSize
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::HasFocus
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertDialog::PreTranslateMessage
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertDialog class
ms.assetid: a53c60aa-9607-485b-b826-ec64962075f6
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
ms.openlocfilehash: a782b48c842bf7cf79b0c01a527132b18700535b
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertdialog-class"></a>CMFCDesktopAlertDialog (classe)
Le `CMFCDesktopAlertDialog` classe est utilisée conjointement avec la [CMFCDesktopAlertWnd classe](../../mfc/reference/cmfcdesktopalertwnd-class.md) pour afficher une boîte de dialogue personnalisée dans une fenêtre contextuelle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDesktopAlertDialog : public CDialogEx  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertDialog::CreateFromParams](#createfromparams)||  
|[CMFCDesktopAlertDialog::GetDlgSize](#getdlgsize)||  
|[CMFCDesktopAlertDialog::HasFocus](#hasfocus)||  
|[CMFCDesktopAlertDialog::PreTranslateMessage](#pretranslatemessage)|(Substitue `CDialogEx::PreTranslateMessage`.)|  
  
### <a name="remarks"></a>Notes  
 Pour afficher une boîte de dialogue personnalisé dans une fenêtre contextuelle, procédez comme suit :  
  
1.  Dérivez une classe de `CMFCDesktopAlertDialog`.  
  
2.  Créez un modèle de boîte de dialogue enfant dans les ressources du projet.  
  
3.  Appelez [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) avec l’ID de ressource de modèle de la boîte de dialogue et un pointeur vers les informations de classe d’exécution de la classe dérivée en tant que paramètres.  
  
4.  Programmez la boîte de dialogue personnalisée de sorte qu'elle traite toutes les notifications en provenance des contrôles hébergés ou programmez les contrôles hébergés de sorte qu'ils traitent directement ces notifications.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCDesktopAlertDialog](../../mfc/reference/cmfcdesktopalertdialog-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDesktopAlertDialog.h  
  
##  <a name="createfromparams"></a>CMFCDesktopAlertDialog::CreateFromParams  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CreateFromParams(
    CMFCDesktopAlertWndInfo& params,  
    CMFCDesktopAlertWnd* pParent);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `params`  
 [in] `pParent`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="getdlgsize"></a>CMFCDesktopAlertDialog::GetDlgSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CSize GetDlgSize();
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="hasfocus"></a>CMFCDesktopAlertDialog::HasFocus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="pretranslatemessage"></a>CMFCDesktopAlertDialog::PreTranslateMessage  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMsg`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd (classe)](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWndInfo (classe)](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)   
 [CDialogEx (classe)](../../mfc/reference/cdialogex-class.md)

