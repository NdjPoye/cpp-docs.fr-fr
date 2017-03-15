---
title: Classe de CMFCSpinButtonCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCSpinButtonCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCSpinButtonCtrl class
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
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
ms.openlocfilehash: c1832062461f2ed53df07a72428089179ed493ab
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl (classe)
La `CMFCSpinButtonCtrl` classe prend en charge un gestionnaire visuel qui dessine un contrôle de bouton toupie (spin).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCSpinButtonCtrl : public CSpinButtonCtrl  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|Constructeur par défaut.|  
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCSpinButtonCtrl::OnDraw](#ondraw)|Redessine le contrôle de bouton toupie (spin) actuel.|  
  
## <a name="remarks"></a>Remarques  
 Pour utiliser un gestionnaire visuel pour dessiner un contrôle de bouton toupie (spin) dans votre application, remplacez toutes les instances de la `CSpinButtonCtrl` classe avec la `CMFCSpinButtonCtrl` classe.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment créer un objet de la `CMFCSpinButtonCtrl` classe son `Create` (méthode).  
  
 [!code-cpp[NVC_MFC_RibbonApp&#25;](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)  
  
 [CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxspinbuttonctrl.h  
  
##  <a name="a-nameondrawa--cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCSpinButtonCtrl::OnDraw  
 Redessine le contrôle de bouton toupie (spin) actuel.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle la `CMFCSpinButtonCtrl::OnPaint` méthode pour gérer les [CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint) message et que méthode appelle à son tour cette `CMFCSpinButtonCtrl::OnDraw` (méthode). Substituez cette méthode pour personnaliser la façon dont le framework Dessine le contrôle de bouton toupie (spin).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager (classe)](../../mfc/reference/cmfcvisualmanager-class.md)

