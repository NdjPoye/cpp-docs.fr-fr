---
title: Classe de CMFCLinkCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCLinkCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCLinkCtrl class
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
caps.latest.revision: 27
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
ms.openlocfilehash: 8c926c0ef611470b137d2bb897c012a85645c90c
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl (classe)
La `CMFCLinkCtrl` classe affiche un bouton sous la forme d’un lien hypertexte et appelle la cible du lien lorsque l’utilisateur clique sur le bouton.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCLinkCtrl : public CMFCButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCLinkCtrl::SetURL](#seturl)|Affiche une URL spécifiée comme texte du bouton.|  
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|Définit le protocole implicit (par exemple, « http : ») de l’URL.|  
|[CMFCLinkCtrl::SizeToContent](#sizetocontent)|Redimensionne le bouton pour contenir le texte du bouton ou bitmap.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|Appelé par l’infrastructure avant que le rectangle de focus du bouton est dessiné.|  
  
## <a name="remarks"></a>Remarques  
 Lorsque vous cliquez sur un bouton qui est dérivé de la `CMFCLinkCtrl` (classe), l’infrastructure passe l’URL du bouton en tant que paramètre à la `ShellExecute` (méthode). Le `ShellExecute` méthode ouvre la cible de l’URL.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment définir la taille d’un `CMFCLinkCtrl` objet et comment définir une url et une info-bulle dans un `CMFCLinkCtrl` objet. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#9;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#10;](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxlinkctrl.h  
  
##  <a name="a-nameondrawfocusrecta--cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCLinkCtrl::OnDrawFocusRect  
 Appelé par l’infrastructure avant que le rectangle de focus du bouton est dessiné.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 [in] `rectClient`  
 Un rectangle qui délimite le contrôle de lien.  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode lorsque vous souhaitez utiliser votre propre code pour dessiner le rectangle de focus du bouton.  
  
##  <a name="a-nameseturla--cmfclinkctrlseturl"></a><a name="seturl"></a>CMFCLinkCtrl::SetURL  
 Affiche une URL spécifiée comme texte du bouton.  
  
```  
void SetURL(LPCTSTR lpszURL);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszURL`  
 Le texte de bouton à afficher.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameseturlprefixa--cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>CMFCLinkCtrl::SetURLPrefix  
 Définit le protocole implicit (par exemple, « http : ») de l’URL.  
  
```  
void SetURLPrefix(LPCTSTR lpszPrefix);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszPrefix`  
 Le préfixe du protocole d’URL.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour définir le préfixe d’URL. Le préfixe n’est pas affiché dans l’image de, mais vous pouvez l’utiliser pour accéder à la cible de l’URL.  
  
##  <a name="a-namesizetocontenta--cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>CMFCLinkCtrl::SizeToContent  
 Redimensionne le bouton pour contenir le texte du bouton ou bitmap.  
  
```  
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,  
    BOOL bHCenter=FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bVCenter`  
 `TRUE`Pour centrer le texte et bouton bitmap verticalement entre le haut et bas du contrôle de lien ; dans le cas contraire, `FALSE`. La valeur par défaut est `FALSE`.  
  
 [in] `bHCenter`  
 `TRUE`Pour centrer le texte et bouton bitmap horizontalement entre les côtés gauche et droit du contrôle de lien ; dans le cas contraire, `FALSE`. La valeur par défaut est `FALSE`.  
  
### <a name="return-value"></a>Valeur de retour  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui contient la nouvelle taille du contrôle de lien.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CLinkCtrl (classe)](../../mfc/reference/clinkctrl-class.md)   
 [CMFCButton (classe)](../../mfc/reference/cmfcbutton-class.md)

