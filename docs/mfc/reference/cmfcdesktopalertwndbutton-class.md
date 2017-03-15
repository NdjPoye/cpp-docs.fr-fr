---
title: Classe de CMFCDesktopAlertWndButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCDesktopAlertWndButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCDesktopAlertWndButton class
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
caps.latest.revision: 23
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
ms.openlocfilehash: 52294143c6caf5a8e0458c152540c41f7df78c57
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton (classe)
Permet de boutons à ajouter à une boîte de dialogue alerte sur le bureau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCDesktopAlertWndButton : public CMFCButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|Constructeur par défaut.|  
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|||  
|-|-|  
|Nom|Description|  
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|Détermine si le bouton est affiché dans la zone de légende de la boîte de dialogue d’alerte.|  
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|Détermine si le bouton ferme la boîte de dialogue d’alerte.|  
  
### <a name="data-members"></a>Membres de données  
  
|||  
|-|-|  
|Nom|Description|  
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|Valeur booléenne qui spécifie si le bouton est affiché dans la zone de légende de la boîte de dialogue d’alerte.|  
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|Valeur booléenne qui spécifie si le bouton ferme la boîte de dialogue d’alerte.|  
  
### <a name="remarks"></a>Notes  
 Par défaut, le constructeur affecte la `m_bIsCaptionButton` et `m_bIsCloseButton` membres de données `FALSE`. Le parent `CMFCDesktopAlertDialog` jeux d’objets `m_bIsCaptionButton` à `TRUE` si le bouton est placé dans la zone de légende de la boîte de dialogue d’alerte. Le `CMFCDesktopAlertDialog` classe crée un `CMFCDesktopAlertWndButton` objet qui sert le bouton qui ferme la boîte de dialogue Alerte de zone et définit `m_bIsCloseButton` à `TRUE`.  
  
 Ajouter `CMFCDesktopAlertWndButton` des objets à un `CMFCDesktopAlertDialog` vous ajoutez un bouton de l’objet. Pour plus d’informations sur `CMFCDesktopAlertDialog`, consultez [CMFCDesktopAlertDialog classe](../../mfc/reference/cmfcdesktopalertdialog-class.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `SetImage` méthode dans la `CMFCDesktopAlertWndButton` classe. Cet extrait de code fait partie de la [exemple de démonstration alerte bureau](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo n °&4;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DesktopAlertDemo n °&5;](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdesktopalertwnd.h  
  
##  <a name="a-nameiscaptionbuttona--cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a>CMFCDesktopAlertWndButton::IsCaptionButton  
 Détermine si le bouton est affiché dans la zone de légende de la boîte de dialogue d’alerte.  
  
```  
BOOL IsCaptionButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton est affiché dans la zone de légende de la boîte de dialogue d’alerte ; Sinon, 0.  
  
##  <a name="a-nameisclosebuttona--cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a>CMFCDesktopAlertWndButton::IsCloseButton  
 Détermine si le bouton ferme la boîte de dialogue d’alerte.  
  
```  
BOOL IsCloseButton() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le bouton ferme la boîte de dialogue d’alerte ; Sinon, 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCDesktopAlertDialog (classe)](../../mfc/reference/cmfcdesktopalertdialog-class.md)

