---
title: Classe de CMFCMenuButton | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMenuButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCMenuButton class
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 65c334ce68dbbbae2b21da2c40aa9420cdeb51bd
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcmenubutton-class"></a>CMFCMenuButton, Classe
Bouton qui affiche un menu contextuel et signale les sélections de l'utilisateur dans les menus.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCMenuButton::CMFCMenuButton](#cmfcmenubutton)|Construit un objet `CMFCMenuButton`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCMenuButton::PreTranslateMessage](#pretranslatemessage)|Appelé par l’infrastructure pour convertir des messages de fenêtre avant leur distribution. (Substitue `CMFCButton::PreTranslateMessage`.)|  
|[CMFCMenuButton::SizeToContent](#sizetocontent)|Modifie la taille du bouton en fonction de sa taille text et image.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCMenuButton::m_bOSMenu](#m_bosmenu)|Spécifie s’il faut afficher le menu contextuel du système par défaut ou utilisez [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).|  
|[CMFCMenuButton::m_bRightArrow](#m_brightarrow)|Spécifie si le menu contextuel s’affiche en dessous ou à droite du bouton.|  
|[CMFCMenuButton::m_bStayPressed](#m_bstaypressed)|Spécifie si le bouton de menu modifie son état une fois que l’utilisateur relâche le bouton.|  
|[CMFCMenuButton::m_hMenu](#m_hmenu)|Handle vers le menu Windows attaché.|  
|[CMFCMenuButton::m_nMenuResult](#m_nmenuresult)|L’utilisateur a un identificateur qui indique à quel élément sélectionné dans le menu contextuel.|  
  
## <a name="remarks"></a>Remarques  
 Le `CMFCMenuButton` classe est dérivée de la [CMFCButton classe](../../mfc/reference/cmfcbutton-class.md) , à son tour, dérivée de la [CButton classe](../../mfc/reference/cbutton-class.md). Par conséquent, vous pouvez utiliser `CMFCMenuButton` dans votre code de la même manière que vous utiliseriez `CButton`.  
  
 Lorsque vous créez un `CMFCMenuButton`, vous devez passer un handle pour le menu contextuel associé. Ensuite, appelez la fonction `CMFCMenuButton::SizeToContent`. `CMFCMenuButton::SizeToContent`vérifie que la taille du bouton est suffisante pour inclure une flèche qui pointe vers l’emplacement où la fenêtre contextuelle apparaît - à savoir, en dessous ou à droite du bouton.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment définir le handle du menu lié au bouton et redimensionner le bouton en fonction de sa taille text et image dans le menu contextuel qui est affichée par l’infrastructure. Cet extrait de code fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#38;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls n °&39;](../../mfc/reference/codesnippet/cpp/cmfcmenubutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmenubutton.h  
  
##  <a name="a-namecmfcmenubuttona--cmfcmenubuttoncmfcmenubutton"></a><a name="cmfcmenubutton"></a>CMFCMenuButton::CMFCMenuButton  
 Construit un nouveau [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md) objet.  
  
```  
CMFCMenuButton();
```  
  
##  <a name="a-namembosmenua--cmfcmenubuttonmbosmenu"></a><a name="m_bosmenu"></a>CMFCMenuButton::m_bOSMenu  
 Une variable membre de type Boolean qui indique le menu contextuel affiche de l’infrastructure.  
  
```  
BOOL m_bOSMenu;  
```  
  
### <a name="remarks"></a>Remarques  
 Si `m_bOSMenu` est `TRUE`, le framework appelle la `TrackPopupMenu` méthode pour cet objet. Sinon, le framework appelle [CContextMenuManager::TrackPopupMenu](../../mfc/reference/ccontextmenumanager-class.md#trackpopupmenu).  
  
##  <a name="a-namembrightarrowa--cmfcmenubuttonmbrightarrow"></a><a name="m_brightarrow"></a>CMFCMenuButton::m_bRightArrow  
 Une variable de membre de type Boolean qui indique l’emplacement du menu contextuel.  
  
```  
BOOL m_bRightArrow;  
```  
  
### <a name="remarks"></a>Notes  
 Lorsque l’utilisateur appuie sur le bouton de menu, l’application affiche un menu contextuel. L’infrastructure affiche le menu contextuel en cliquant sur le bouton ou à droite du bouton. Le bouton possède également une petite flèche qui indique où le menu contextuel s’affiche. Si `m_bRightArrow` est `TRUE`, l’infrastructure affiche le menu contextuel à droite du bouton. Sinon, elle affiche le menu contextuel sous le bouton.  
  
##  <a name="a-namembstaypresseda--cmfcmenubuttonmbstaypressed"></a><a name="m_bstaypressed"></a>CMFCMenuButton::m_bStayPressed  
 Une variable de membre de type Boolean qui indique si le bouton de menu apparaît enfoncée alors que l’utilisateur effectue une sélection dans le menu contextuel.  
  
```  
BOOL m_bStayPressed;  
```  
  
### <a name="remarks"></a>Notes  
 Si le `m_bStayPressed` membre est `FALSE`, le bouton de menu ne pas devenir activé et que les utilisations clique sur le bouton. Dans ce cas, l’infrastructure affiche uniquement dans le menu contextuel.  
  
 Si le `m_bStayPressed` membre est `TRUE`, le bouton de menu est activé lorsque l’utilisateur clique sur le bouton. Il reste enfoncé jusqu'à une fois que l’utilisateur ferme le menu contextuel, en effectuant une sélection ou de l’annulation.  
  
##  <a name="a-namemhmenua--cmfcmenubuttonmhmenu"></a><a name="m_hmenu"></a>CMFCMenuButton::m_hMenu  
 Le handle du menu attaché.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="remarks"></a>Notes  
 L’infrastructure affiche le menu indiqué par cette variable membre lorsque l’utilisateur clique sur le bouton de menu.  
  
##  <a name="a-namemnmenuresulta--cmfcmenubuttonmnmenuresult"></a><a name="m_nmenuresult"></a>CMFCMenuButton::m_nMenuResult  
 Entier qui indique quel élément de l’utilisateur sélectionne dans le menu contextuel.  
  
```  
int m_nMenuResult;  
```  
  
### <a name="remarks"></a>Remarques  
 La valeur de cette variable membre est égal à zéro si l’utilisateur annule le menu sans effectuer de sélection, ou si une erreur se produit.  
  
##  <a name="a-namepretranslatemessagea--cmfcmenubuttonpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuButton::PreTranslateMessage  
 Appelé par l’infrastructure pour convertir des messages de fenêtre avant leur distribution.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pMsg`  
 Pointe vers une [MSG](../../mfc/reference/msg-structure1.md) structure qui contient le message à traiter.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message a été converti et ne doit pas être distribué ; 0 si le message n’était pas traduit et doit être distribué.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesizetocontenta--cmfcmenubuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCMenuButton::SizeToContent  
 Modifie la taille du bouton en fonction de sa taille du texte et la taille de l’image.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bCalcOnly`  
 Un paramètre booléen qui indique si cette méthode permet de redimensionner le bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui spécifie la nouvelle taille du bouton.  
  
### <a name="remarks"></a>Remarques  
 Si vous appelez cette fonction et `bCalcOnly` est `TRUE`, `SizeToContent` calcule uniquement la nouvelle taille du bouton.  
  
 La nouvelle taille du bouton est calculée en fonction de flèche, l’image et le texte du bouton. Le framework ajoute également des marges prédéfinies de 10 pixels du bord horizontal et de 5 pixels du bord vertical.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCButton (classe)](../../mfc/reference/cmfcbutton-class.md)

