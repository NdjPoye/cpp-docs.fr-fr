---
title: Classe de CMFCDesktopAlertWndInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndInfo class
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
caps.latest.revision: 26
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
ms.openlocfilehash: 7013a7c9b29c6dc9e6324ca0490a667ed79c88f7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo (classe)
Le `CMFCDesktopAlertWndInfo` classe est utilisée avec la [CMFCDesktopAlertWnd classe](../../mfc/reference/cmfcdesktopalertwnd-class.md). Elle spécifie les contrôles qui sont affichés si la fenêtre d'alerte sur le Bureau s'affiche.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDesktopAlertWndInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon)|Un handle de l’icône qui s’affiche.|  
|[CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid)|L’ID de commande associé à un lien dans la fenêtre d’alerte de bureau.|  
|[CMFCDesktopAlertWndInfo::m_strText](#m_strtext)|Le texte affiché dans la fenêtre d’alerte de bureau.|  
|[CMFCDesktopAlertWndInfo::m_strURL](#m_strurl)|Le lien s’affiche dans la fenêtre alerte bureau.|  
  
## <a name="remarks"></a>Remarques  
 Le `CMFCDesktopAlertWndInfo` classe est passée à la [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) méthode pour spécifier les éléments qui sont affichés dans la boîte de dialogue par défaut de la fenêtre Bureau de l’alerte. La boîte de dialogue par défaut peut contenir trois éléments :  
  
-   Une icône qui est définie en appelant [CMFCDesktopAlertWndInfo::m_hIcon](#m_hicon).  
  
-   Une étiquette ou un message texte, qui est défini en appelant [CMFCDesktopAlertWndInfo::m_strText](#m_strtext).  
  
-   Un lien, qui est défini en appelant [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl). Pour définir la commande est exécutée lorsque l’utilisateur clique sur le lien, appelez [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid).  
  
 Si la boîte de dialogue par défaut n’est pas suffisante, vous pouvez créer une boîte de dialogue personnalisée et transmettez-le à la [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) méthode au lieu d’utiliser cette classe. Pour plus d’informations, consultez [CMFCDesktopAlertDialog classe](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser les différents membres de la `CMFCDesktopAlertWndInfo` classe. L’exemple montre comment définir le handle de l’icône qui s’affiche, le texte qui s’affiche dans la fenêtre d’alerte de bureau, le lien s’affiche dans la fenêtre alerte bureau et l’ID de commande qui est associé à un lien dans la fenêtre d’alerte de bureau. Cet exemple fait partie de la [exemple de démonstration alerte bureau](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo n °&3;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDesktopAlertDialog.h  
  
##  <a name="operator_eq"></a>CMFCDesktopAlertWndInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `src`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_hicon"></a>CMFCDesktopAlertWndInfo::m_hIcon  
 Un handle de l’icône qui s’affiche.  
  
```  
HICON m_hIcon;  
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_nurlcmdid"></a>CMFCDesktopAlertWndInfo::m_nURLCmdID  
 L’ID de commande associé à un lien dans la fenêtre d’alerte de bureau.  
  
```  
UINT m_nURLCmdID;  
```  
  
### <a name="remarks"></a>Remarques  
 L’ID de commande est envoyé au propriétaire de la fenêtre contextuelle lorsque l’utilisateur clique sur le lien spécifié par [CMFCDesktopAlertWndInfo::m_strURL](#m_strurl).  
  
##  <a name="m_strtext"></a>CMFCDesktopAlertWndInfo::m_strText  
 Le texte affiché dans la fenêtre d’alerte de bureau.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_strurl"></a>CMFCDesktopAlertWndInfo::m_strURL  
 Le lien s’affiche dans la fenêtre alerte bureau.  
  
```  
CString m_strURL;  
```  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur clique sur le lien, la commande ayant la [CMFCDesktopAlertWndInfo::m_nURLCmdID](#m_nurlcmdid) ID de commande sera envoyé au propriétaire de la fenêtre contextuelle.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertWnd (classe)](../../mfc/reference/cmfcdesktopalertwnd-class.md)   
 [CMFCDesktopAlertWnd::Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)   
 [CMFCDesktopAlertDialog (classe)](../../mfc/reference/cmfcdesktopalertdialog-class.md)

