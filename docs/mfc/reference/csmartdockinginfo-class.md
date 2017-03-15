---
title: Classe de CSmartDockingInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSmartDockingInfo
dev_langs:
- C++
helpviewer_keywords:
- CSmartDockingInfo class
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
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
ms.openlocfilehash: 9ae735b202299d26b98ec763f65c3f8772d9b914
ms.lasthandoff: 02/24/2017

---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo (classe)
Définit l'apparence des marqueurs d'ancrage intelligents.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Constructeur par défaut.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Copie les paramètres d’info de d’ancrage actives en cours dans les [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) objet.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Spécifie s’il faut utiliser la couleur de thème actuel lorsque l’infrastructure affiche des marqueurs d’ancrage intelligents.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Spécifie la couleur d’arrière-plan de base des marqueurs d’ancrage intelligents.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Spécifie la couleur qui remplace `m_clrToneSrc` dans des bitmaps marqueur d’ancrage intelligents.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Spécifie la couleur des bitmaps de marqueur d’ancrage intelligents.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Spécifie la couleur des bitmaps de marqueur d’ancrage intelligents lorsqu’ils sont transparents.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Spécifie le décalage des marqueurs d’ancrage actifs depuis les limites du rectangle du groupe central du groupe central.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Spécifie la taille totale de tous les marqueurs d’ancrage actifs dans un groupe.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Définit les ID des bitmaps pour les marqueurs d’ancrage actifs qui ne sont pas mises en surbrillance par le framework de ressources.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Définit les ID des bitmaps pour les marqueurs d’ancrage actifs qui sont mises en surbrillance par le framework de ressources.|  
  
## <a name="remarks"></a>Remarques  
 Les poignées de framework smart marqueurs d’ancrage en interne. L’illustration suivante montre les marqueurs d’ancrage actifs standards :  
  
 ![Marqueurs d’ancrage actifs standard](../../mfc/reference/media/nextsdmarkers.png "nextsdmarkers")  
  
 Dans cette figure, l’image sur la gauche montre un marqueur d’ancrage intelligents groupe central qui ne dispose pas d’ancrage d’un onglet est activé. L’image du milieu affiche un marqueur d’ancrage intelligents à droite. L’image de droite affiche un marqueur d’ancrage intelligents groupe central équipé d’ancrage d’un onglet est activé. Le marqueur d’ancrage intelligents groupe central a un bitmap principale et cinq smart bitmaps de marqueur d’ancrage.  
  
 Vous pouvez personnaliser les paramètres suivants de marqueurs d’ancrage actifs :  
  
-   Couleur. Par exemple, vous pouvez remplacer la couleur bleue des marqueurs dans la figure par n’importe quelle couleur définie par l’utilisateur.  
  
-   Couleur de transparence.  
  
-   Décalage d’un marqueur d’ancrage intelligent dans le groupe central à partir de la bordure du rectangle englobant.  
  
-   Bitmap principal qui représente le groupe central.  
  
-   Les bitmaps qui représente les marqueurs d’ancrage actifs standard et en surbrillance.  
  
 L’illustration suivante montre un exemple de marqueurs d’ancrage actifs qui ont été personnalisées :  
  
 ![Marqueurs d’ancrage actif personnalisés](../../mfc/reference/media/nextsdmarkerscustom.png "nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxDockingManager.h  
  
##  <a name="a-namecopytoa--csmartdockinginfocopyto"></a><a name="copyto"></a>CSmartDockingInfo::CopyTo  
 Copie les paramètres d’ancrage intelligents dans fourni [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) objet.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Paramètres  
 [out] `params`  
 Un objet de type `CSmartDockingInfo` qui est rempli avec les paramètres d’ancrage intelligents.  
  
##  <a name="a-namembusethemecolorinshadinga--csmartdockinginfombusethemecolorinshading"></a><a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading  
 Spécifie s’il faut utiliser la couleur de thème actuel lorsque l’infrastructure affiche des marqueurs d’ancrage intelligents.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Notes  
 Si `TRUE`, les marqueurs sont dessinées à l’aide de la couleur de thème actuel ; sinon, les marqueurs sont dessinés avec une couleur bleu clair.  
  
 La valeur par défaut est `FALSE`.  
  
##  <a name="a-namemclrbasebackgrounda--csmartdockinginfomclrbasebackground"></a><a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground  
 Spécifie la couleur d’arrière-plan de base des marqueurs d’ancrage intelligents.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="a-namemclrtonedesta--csmartdockinginfomclrtonedest"></a><a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest  
 Spécifie la couleur qui doit remplacer `m_clrToneSrc` dans des bitmaps marqueur d’ancrage intelligents.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez cette valeur pour modifier la couleur du marqueur bitmaps par programmation. Par exemple, si vous souhaitez modifier la couleur des marqueurs standards fournis avec le framework, définissez cette valeur sur la couleur souhaitée. Par défaut, [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) a la valeur RVB (61, 123, 241) (une couleur bleue).  
  
 Pour modifier la couleur des marqueurs personnalisés, vous devez spécifier les deux `m_clrToneDest` et `m_clrToneSrc`.  
  
##  <a name="a-namemclrtonesrca--csmartdockinginfomclrtonesrc"></a><a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc  
 Spécifie la couleur des bitmaps de marqueur d’ancrage intelligents.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Notes  
 Cette valeur uniquement lorsque vous souhaitez remplacer la couleur d’une bitmap personnalisée avec une autre couleur. Il est inutile de définir cette valeur si vous modifiez la couleur de la norme (framework fournie) marqueur.  
  
 Utilisez `(COLORREF)-1` pour renseigner un membre du groupe d’ancrage intelligent.  
  
##  <a name="a-namemclrtransparenta--csmartdockinginfomclrtransparent"></a><a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent  
 Spécifie la couleur des bitmaps de marqueur d’ancrage intelligents lorsqu’ils sont transparents.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Remarques  
 Vous devez définir cette valeur lorsque vous affichez des marqueurs personnalisés et les bitmaps personnalisés dans le groupe d’ancrage.  
  
##  <a name="a-namemncentralgroupoffseta--csmartdockinginfomncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset  
 Spécifie le décalage entre le groupe central de marqueurs d’ancrage actifs et les limites du rectangle du groupe central.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Remarques  
 Spécifiez cette valeur si vous souhaitez modifier le décalage par défaut entre les marqueurs personnalisés et les limites du groupe central de marqueurs d’ancrage intelligents. Le décalage par défaut est de 5 pixels.  
  
##  <a name="a-namemsizetotala--csmartdockinginfomsizetotal"></a><a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal  
 Spécifie la taille totale d’un rectangle qui englobe tous les marqueurs d’ancrage actifs dans le groupe central.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Remarques  
 Définissez `m_sizeTotal` à la taille du rectangle englobant de la marque du groupe central. Vous devez spécifier cette valeur si vous utilisez des images personnalisées pour les marqueurs.  
  
##  <a name="a-namemuimarkerbmpresida--csmartdockinginfomuimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID  
 Définit l’ID des bitmaps qui sont utilisés pour les marqueurs d’ancrage intelligents personnalisées non mis en surbrillance de la ressource.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Remarques  
 Remplissez avec les ID des bitmaps représentant les marqueurs d’ancrage intelligents de ressources. `AFX_SD_MARKERS_NUM`est actuellement défini comme 5. Vous remplissez le tableau comme suit :  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="a-namemuimarkerlightbmpresida--csmartdockinginfomuimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Définit les ID des bitmaps qui sont utilisés pour les marqueurs d’ancrage intelligents personnalisées en surbrillance de ressources.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Remarques  
 Remplissez avec les ID des bitmaps représentant les marqueurs d’ancrage actifs en surbrillance de ressources. `AFX_SD_MARKERS_NUM`est actuellement défini comme 5. Vous remplissez le tableau comme suit :  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject (classe)](../../mfc/reference/cobject-class.md)

