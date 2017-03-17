---
title: Classe de CFormView | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
dev_langs:
- C++
helpviewer_keywords:
- views, containing controls
- CFormView class
- form views
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
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
ms.openlocfilehash: 82b38b04aa3cf2368d41ee20847c952c3082d4e4
ms.lasthandoff: 02/24/2017

---
# <a name="cformview-class"></a>Classe de CFormView
Classe de base utilisée pour les modes formulaire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFormView : public CScrollView  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CFormView::CFormView](#cformview)|Construit un objet `CFormView`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|Utilisé pour la synchronisation pendant l’initialisation.|  
  
## <a name="remarks"></a>Remarques  
 En substance, me mode Formulaire est une vue qui contient des contrôles. La disposition de ces contrôles est basée sur une ressource de modèle de boîte de dialogue. Utilisez `CFormView` si vous voulez des formulaires dans votre application. Ces vues prennent en charge le défilement, le cas échéant, à l’aide de la [CScrollView](../../mfc/reference/cscrollview-class.md) fonctionnalité.  
  
 Lorsque vous êtes [création d’une Application basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md), vous pouvez baser sa classe d’affichage sur `CFormView`, rend une application basée sur les formulaires.  
  
 Vous pouvez également insérer de nouvelles [rubriques relatives aux formulaires](../../mfc/form-views-mfc.md) dans des applications basé sur la vue de document. Même si, au départ, votre application ne prend pas en charge les formulaires, Visual C++ ajoute cette prise en charge du moment que vous insérez un nouveau formulaire.  
  
 L'Assistant Application MFC et la commande Ajouter une classe sont les méthodes recommandées pour créer des applications basées sur les formulaires. Si vous avez besoin créer une application basée sur les formulaires sans l’aide de ces méthodes, consultez [création d’une Application basée sur les formulaires](../../mfc/reference/creating-a-forms-based-mfc-application.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxext.h  
  
##  <a name="cformview"></a>CFormView::CFormView  
 Construit un objet `CFormView`.  
  
```  
CFormView(LPCTSTR lpszTemplateName);  
CFormView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszTemplateName`  
 Contient une chaîne terminée par le caractère null qui correspond au nom d’une ressource modèle de boîte de dialogue.  
  
 `nIDTemplate`  
 Contient le numéro d’ID d’une ressource modèle de boîte de dialogue.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous créez un objet d’un type dérivé de `CFormView`, appelez un des constructeurs pour créer l’objet d’affichage et d’identifier la ressource de boîte de dialogue sur laquelle repose la vue. Vous pouvez identifier la ressource par son nom (passez une chaîne comme argument au constructeur) ou par son ID (passer un entier non signé comme argument).  
  
 Les contrôles de fenêtre et enfant en mode formulaire ne sont pas créés tant que `CWnd::Create` est appelée. `CWnd::Create`est appelé par l’infrastructure en tant que partie du document et la vue processus de création, pilotée par le modèle de document.  
  
> [!NOTE]
>  Votre classe dérivée *doit* fournir son propre constructeur. Dans le constructeur, appelez le constructeur, `CFormView::CFormView`, avec le nom de la ressource ou l’ID en tant qu’argument comme indiqué dans la rubrique de présentation (classe).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#90;](../../mfc/codesnippet/cpp/cformview-class_1.h)]  
  
 [!code-cpp[NVC_MFCDocView&#91;](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]  
  
##  <a name="isinitdlgcompleted"></a>CFormView::IsInitDlgCompleted  
 Utilisé par MFC pour faire en sorte que l'initialisation se termine avant que d'autres opérations soient entreprises.  
  
```  
BOOL IsInitDlgCompleted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 True si la fonction d'initialisation de cette boîte de dialogue a abouti.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC SNAPVW](../../visual-cpp-samples.md)   
 [Exemple MFC VIEWEX](../../visual-cpp-samples.md)   
 [CScrollView (classe)](../../mfc/reference/cscrollview-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDialog (classe)](../../mfc/reference/cdialog-class.md)   
 [CScrollView (classe)](../../mfc/reference/cscrollview-class.md)

