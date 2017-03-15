---
title: Classe de CMFCToolTipInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo class
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
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
ms.openlocfilehash: ed15ce9f3e1abb48c0a6c4eacdf662cc2ef3f9c9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo (classe)
Stocke des informations sur l'apparence visuelle des info-bulles.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Variable booléenne qui indique si l'info-bulle a l'aspect d'une bulle.|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Variable booléenne qui indique si les étiquettes d'info-bulle s'affichent en caractères gras.|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Variable booléenne qui indique si l'info-bulle contient une description.|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Variable booléenne qui indique si l'info-bulle contient une icône.|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Variable booléenne qui indique si un séparateur s'affiche entre l'étiquette et la description de l'info-bulle.|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Variable booléenne qui indique si l'info-bulle a des angles arrondis.|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Une variable booléenne qui indique si l’apparence de l’info-bulle doit être contrôlée par un gestionnaire visuel (voir [CMFCVisualManager classe](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Couleur de la bordure de l'info-bulle.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Couleur de l'arrière-plan de l'info-bulle.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Couleur du dégradé dans l'info-bulle.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Couleur du texte de l'info-bulle.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Angle du dégradé dans l'info-bulle.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Largeur maximale, en pixels, de la description figurant dans l'info-bulle.|  
  
## <a name="remarks"></a>Remarques  
 Utilisez [CMFCToolTipCtrl classe](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, et [CTooltipManager classe](../../mfc/reference/ctooltipmanager-class.md) pour implémenter des info-bulles personnalisées dans votre application. Pour obtenir un exemple d’utilisation de ces classes d’info-bulle, consultez le [CMFCToolTipCtrl classe](../../mfc/reference/cmfctooltipctrl-class.md) rubrique.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant montre comment définir les valeurs des différentes variables membres de la classe `CMFCToolTipInfo`.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#42;](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtooltipctrl.h  
  
##  <a name="a-namembballoontooltipa--cmfctooltipinfombballoontooltip"></a><a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip  
 Spécifie le style d’affichage de toutes les info-bulles.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>Remarques  
 `TRUE`Indique que les info-bulles utilisent le style d’info-bulle, `FALSE` indique que les info-bulles utilisent le style rectangulaire.  
  
##  <a name="a-namembboldlabela--cmfctooltipinfombboldlabel"></a><a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel  
 Spécifie si la police du texte info-bulle est en gras.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez ce membre sur `TRUE` pour afficher le texte d’info-bulle en gras, ou `FALSE` pour afficher les étiquettes de l’info-bulle avec police gras.  
  
##  <a name="a-namembdrawdescriptiona--cmfctooltipinfombdrawdescription"></a><a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription  
 Spécifie si chaque info-bulle affiche le texte de description.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>Notes  
 Définissez ce membre sur `TRUE` pour afficher la description, ou `FALSE` pour masquer la description. Vous pouvez spécifier la description dans une info-bulle en appelant [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="a-namembdrawicona--cmfctooltipinfombdrawicon"></a><a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon  
 Spécifie si toutes les info-bulles affichent les icônes.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez ce membre sur `TRUE` pour afficher une icône sur chaque info-bulle, ou `FALSE` pour afficher des info-bulles sans icônes.  
  
##  <a name="a-namembdrawseparatora--cmfctooltipinfombdrawseparator"></a><a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator  
 Indique si chaque info-bulle comporte un séparateur entre son étiquette et sa description.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez ce membre sur `TRUE` pour afficher le séparateur entre l’étiquette d’info-bulle et la description, ou `FALSE` pour afficher des info-bulles sans séparateur.  
  
##  <a name="a-namembroundedcornersa--cmfctooltipinfombroundedcorners"></a><a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners  
 Spécifie si toutes les info-bulles aux angles arrondis.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez ce membre sur `TRUE` pour afficher les angles arrondis sur les info-bulles, ou `FALSE` pour afficher les angles rectangulaires sur des info-bulles.  
  
##  <a name="a-namemclrbordera--cmfctooltipinfomclrborder"></a><a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder  
 Spécifie la couleur des bordures sur toutes les info-bulles.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="a-namemclrfilla--cmfctooltipinfomclrfill"></a><a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill  
 Spécifie la couleur d’arrière-plan de l’info-bulle.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>Remarques  
 Si [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1, la couleur d’arrière-plan info-bulle est `m_clrFill`. Dans le cas contraire, `m_clrFill` spécifie la couleur de début du dégradé et `m_clrFillGradient` spécifie la couleur de la fin du dégradé. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) détermine le sens du dégradé.  
  
##  <a name="a-namemclrfillgradienta--cmfctooltipinfomclrfillgradient"></a><a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient  
 Spécifie la couleur de fin pour un arrière-plan dégradé pour les info-bulles.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>Remarques  
 Si `m_clrFillGradient` est -1, il n’existe aucun dégradé. Sinon, la couleur initiale est spécifiée par [CMFCToolTipInfo::m_clrFill](#m_clrfill) et la couleur de fin de dégradé est spécifiée par `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) détermine le sens du dégradé.  
  
##  <a name="a-namemclrtexta--cmfctooltipinfomclrtext"></a><a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText  
 Spécifie la couleur du texte de toutes les info-bulles.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="a-namemngradientanglea--cmfctooltipinfomngradientangle"></a><a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle  
 Spécifie l’angle auquel un dégradé est dessiné sur l’arrière-plan des info-bulles.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>Remarques  
 `m_nGradientAngle`Spécifie l’angle, en degrés, que le dégradé de l’arrière-plan des info-bulles décalée par rapport à l’horizontale. Si `m_nGradientAngle` est 0, le dégradé est dessiné de gauche à droite. Si `m_nGradientAngle` est comprise entre 1 et 360, le dégradé en rotation vers la droite par le nombre de degrés. Si `m_nGradientAngle` est -1, qui est la valeur par défaut, le dégradé est tracé à partir de haut en bas. Ceci est le même que `m_nGradientAngle` à 90.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` spécifie la couleur de début du dégradé et [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` spécifie la couleur de la fin du dégradé. Si `m_clrFillGradient` est -1, il n’existe aucun dégradé.  
  
##  <a name="a-namemnmaxdescrwidtha--cmfctooltipinfomnmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth  
 Spécifie la largeur maximale de la description qu’il est affiché dans chaque info-bulle. Si la largeur de description dépasse la valeur spécifiée, le texte est encapsulé.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="a-namembvislmanagerthemea--cmfctooltipinfombvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme  
 Spécifie si le Gestionnaire visuel de l’application contrôle l’apparence de toutes les info-bulles.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>Notes  
 Si `m_bVislManagerTheme` est `TRUE`, chaque info-bulle demande un nouveau [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) dans le Gestionnaire visuel de l’application avant qu’ils s’affichent à l’écran et utilise les valeurs de cet objet pour déterminer leur apparence. Les autres membres de votre [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) sont ignorés.  
  
##  <a name="a-nameoperatoreqa--cmfctooltipinfooperator"></a><a name="operator_eq"></a>CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `src`  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Notes  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager (classe)](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl (classe)](../../mfc/reference/cmfctooltipctrl-class.md)

