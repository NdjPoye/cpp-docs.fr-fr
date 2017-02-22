---
title: "CRect (classe) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPCRECT (type de données)"
  - "CRect (classe)"
  - "Opérateur LPRECT"
  - "RECT (structure)"
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRect (classe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Similaire à un Windows [RECT](../../mfc/reference/rect-structure1.md) structure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRect::CRect](#crect__crect)|Construit un objet `CRect`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRect::BottomRight](#crect__bottomright)|Retourne le point en bas à droite de `CRect`.|  
|[CRect::CenterPoint](#crect__centerpoint)|Retourne le point central de `CRect`.|  
|[CRect::CopyRect](#crect__copyrect)|Copie les dimensions d’un rectangle source à `CRect`.|  
|[CRect::DeflateRect](#crect__deflaterect)|Réduit la largeur et la hauteur de `CRect`.|  
|[CRect::EqualRect](#crect__equalrect)|Détermine si `CRect` est égal au rectangle donné.|  
|[CRect::Height](#crect__height)|Calcule la hauteur de `CRect`.|  
|[CRect::InflateRect](#crect__inflaterect)|Augmente la largeur et la hauteur de `CRect`.|  
|[CRect::IntersectRect](#crect__intersectrect)|Jeux de `CRect` égal à l’intersection de deux rectangles.|  
|[CRect::IsRectEmpty](#crect__isrectempty)|Détermine si `CRect` est vide. `CRect` est vide si la largeur ou hauteur ont pour valeur 0.|  
|[CRect::IsRectNull](#crect__isrectnull)|Détermine si le **haut**, **bas**, **gauche**, et **droit** variables de membre sont toujours égaux à 0.|  
|[CRect::MoveToX](#crect__movetox)|Déplace `CRect` à la coordonnée x spécifiée.|  
|[CRect::MoveToXY](#crect__movetoxy)|Déplace `CRect` aux coordonnées x et y spécifiées.|  
|[CRect::MoveToY](#crect__movetoy)|Déplace `CRect` à la coordonnée y spécifiée.|  
|[CRect::NormalizeRect](#crect__normalizerect)|Normalise la hauteur et la largeur de `CRect`.|  
|[CRect::OffsetRect](#crect__offsetrect)|Déplace `CRect` par offsets spécifiés.|  
|[CRect::PtInRect](#crect__ptinrect)|Détermine si le point spécifié se trouve dans `CRect`.|  
|[CRect::SetRect](#crect__setrect)|Définit les dimensions de `CRect`.|  
|[CRect::SetRectEmpty](#crect__setrectempty)|Jeux de `CRect` à un rectangle vide (toutes les coordonnées est égal à 0).|  
|[CRect::Size](#crect__size)|Calcule la taille de `CRect`.|  
|[CRect::SubtractRect](#crect__subtractrect)|Soustrait un rectangle d’une autre.|  
|[CRect::TopLeft](#crect__topleft)|Retourne le point supérieur gauche de `CRect`.|  
|[CRect::UnionRect](#crect__unionrect)|Jeux de `CRect` égal à l’union de deux rectangles.|  
|[CRect::Width](#crect__width)|Calcule la largeur de `CRect`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRect::operator-](#crect__operator_-)|Soustrait le décalage donné à partir de `CRect` ou réduit la forme `CRect` et retourne résultant `CRect`.|  
|[CRect::operator LPCRECT](#crect__operator_lpcrect)|Convertit un `CRect` à un **LPCRECT**.|  
|[CRect::operator LPRECT](#crect__operator_lprect)|Convertit un `CRect` à un `LPRECT`.|  
|[CRect::operator ! =](#crect__operator__neq)|Détermine si `CRect` n’est pas égal à un rectangle.|  
|[CRect::operator &amp;](#crect__operator__amp_)|Crée l’intersection de `CRect` et un rectangle et le retourne résultant `CRect`.|  
|[CRect::operator &amp;=](#crect__operator__amp__eq)|Jeux de `CRect` égal à l’intersection de `CRect` et un rectangle.|  
|[CRect::operator |](#crect__operator__or)|Crée l’union de `CRect` et un rectangle et le retourne résultant `CRect`.|  
|[CRect::operator |=](#crect__operator__or_eq)|Jeux de `CRect` égal à l’union de `CRect` et un rectangle.|  
|[CRect::operator +](#crect__operator__add)|Ajoute les offsets donnés à `CRect` ou augmente `CRect` et retourne résultant `CRect`.|  
|[CRect::operator +=](#crect__operator__add_eq)|Ajoute des offsets spécifiés à `CRect` ou augmente `CRect`.|  
|[CRect::operator =](#crect__operator__eq)|Copie les dimensions d’un rectangle à `CRect`.|  
|[CRect::operator =](#crect__operator_-_eq)|Soustrait le décalage spécifié à partir de `CRect` ou réduit la forme `CRect`.|  
|[CRect::operator ==](#crect__operator__eq_eq)|Détermine si `CRect` est égal à un rectangle.|  
  
## <a name="remarks"></a>Notes  
 `CRect` inclut également des fonctions de membre pour manipuler `CRect` objets et Windows `RECT` structures.  
  
 Un `CRect` objet peut être passé comme paramètre de fonction partout où un `RECT` structure **LPCRECT**, ou `LPRECT` peuvent être passés.  
  
> [!NOTE]
>  Cette classe est dérivée de la **tagRECT** structure. (Le nom **tagRECT** est un nom moins couramment utilisés pour le `RECT` structure.) Cela signifie que les membres de données ( **gauche**, **haut**, **droit**, et **bas**) de la `RECT` structure sont les membres de données accessibles de `CRect`.  
  
 Un `CRect` contient des variables de membre qui définissent les points en haut à gauche et en bas à droite d’un rectangle.  
  
 Lorsque vous spécifiez une `CRect`, vous devez être attentif à la construire afin qu’elle est normalisée, en d’autres termes, telles que la valeur de la coordonnée gauche est inférieure à droite et le bord supérieur est inférieure à la partie inférieure. Par exemple, un coin supérieur gauche de (10,10) en bas à droite de (20,20) définit un rectangle normalisé, mais un coin supérieur gauche de (20,20) et bas à droite (10,10) définit un rectangle non normalisées. Si le rectangle n’est pas normalisée nombreuses `CRect` fonctions membres peuvent retourner des résultats incorrects. (Voir [CRect::NormalizeRect](#crect__normalizerect) pour obtenir la liste de ces fonctions.) Avant d’appeler une fonction qui nécessite des rectangles normalisées, vous pouvez normaliser les rectangles non normalisé en appelant le `NormalizeRect` (fonction).  
  
 Soyez prudent lors de la manipulation un `CRect` avec le [CDC::DPtoLP] (.. /Topic/CDC%20Class.MD#cdc__dptolp et [CDC::LPtoDP] (.. Fonctions membres /topic/CDC%20Class.MD#cdc__lptodp. Si le mode de mappage d’un contexte d’affichage est de sorte que l’étendue de y est négatif, comme dans `MM_LOENGLISH`, puis `CDC::DPtoLP` transformera le `CRect` afin que son début est supérieure à la partie inférieure. Les fonctions telles que **hauteur** et **taille** renverra ensuite des valeurs négatives pour la hauteur de l’élément transformé `CRect`, et le rectangle sera non normalisées.  
  
 Lorsque l’utilisation surchargé `CRect` opérateurs, le premier opérande doit être un `CRect`; le second peut être soit un [RECT](../../mfc/reference/rect-structure1.md) structure ou un `CRect` objet.  
  
> [!NOTE]
>  Pour plus d’informations sur partagé classes d’utilitaire (comme `CRect`), consultez [Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltypes.h  
  
##  <a name="a-namecrectbottomrighta-crectbottomright"></a><a name="crect__bottomright"></a>  CRect::BottomRight  
 Les coordonnées sont retournées comme une référence à un [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui est contenue dans `CRect`.  
  
```  
 
CPoint& BottomRight() throw();

const CPoint& BottomRight() const throw();

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les coordonnées de l’angle inférieur droit du rectangle.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez utiliser cette fonction pour obtenir ou définir l’angle inférieur droit du rectangle. Définir l’angle à l’aide de cette fonction sur le côté gauche de l’opérateur d’assignation.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#35](../../atl-mfc-shared/codesnippet/CPP/crect-class_1.cpp)]  
  
##  <a name="a-namecrectcenterpointa-crectcenterpoint"></a><a name="crect__centerpoint"></a>  CRect::CenterPoint  
 Calcule le point central de `CRect` en ajoutant les valeurs de gauche et droite et divisant par deux et les valeurs supérieure et inférieure divisant par deux.  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CPoint` objet qui est le point central de `CRect`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#36](../../atl-mfc-shared/codesnippet/CPP/crect-class_2.cpp)]  
  
##  <a name="a-namecrectcopyrecta-crectcopyrect"></a><a name="crect__copyrect"></a>  CRect::CopyRect  
 Copie le `lpSrcRect` rectangle dans `CRect`.  
  
```  
 
void CopyRect(
LPCRECT   
lpSrcRect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpSrcRect`  
 Pointe vers le [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet doit être copié.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#37](../../atl-mfc-shared/codesnippet/CPP/crect-class_3.cpp)]  
  
##  <a name="a-namecrectcrecta-crectcrect"></a><a name="crect__crect"></a>  CRect::CRect  
 Construit un objet `CRect`.  
  
```  
 
    CRect() throw();
CRect(
 int    
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();
CRect(
 const RECT& 
    srcRect) throw();
CRect(
 LPCRECT    
    lpSrcRect) throw();
CRect(
 POINT    
    point ,  
    SIZE 
    size) throw();
CRect(
 POINT    
    topLeft ,  
    POINT 
    bottomRight) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *l*  
 Spécifie la position gauche de `CRect`.  
  
 *t*  
 Spécifie la partie supérieure de `CRect`.  
  
 *r*  
 Spécifie la position à droite de `CRect`.  
  
 *b*  
 Spécifie la partie inférieure de `CRect`.  
  
 *srcRect*  
 Fait référence à la [RECT](../../mfc/reference/rect-structure1.md) structure avec les coordonnées de `CRect`.  
  
 `lpSrcRect`  
 Pointe vers le `RECT` structure avec les coordonnées de `CRect`.  
  
 `point`  
 Spécifie le point d’origine du rectangle doit être construite. Correspond à l’angle supérieur gauche.  
  
 `size`  
 Spécifie le déplacement à partir du coin supérieur gauche au coin inférieur droit du rectangle doit être construite.  
  
 *en haut à gauche*  
 Spécifie la position de l’angle supérieur gauche de `CRect`.  
  
 *en bas à droite*  
 Spécifie la position en bas à droite de `CRect`.  
  
### <a name="remarks"></a>Notes  
 Si aucun argument n’est fourni, **gauche**, **haut**, **droit**, et **bas** membres ne sont pas initialisés.  
  
 Le `CRect`( **const RECT &**) et `CRect`( **LPCRECT**) constructeurs effectuer un [CopyRect](#crect__copyrect). Les autres constructeurs initialisent les variables de membre de l’objet directement.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#38](../../atl-mfc-shared/codesnippet/CPP/crect-class_4.cpp)]  
  
##  <a name="a-namecrectdeflaterecta-crectdeflaterect"></a><a name="crect__deflaterect"></a>  CRect::DeflateRect  
 `DeflateRect` réduit la forme `CRect` en déplaçant ses côtés vers son centre.  
  
```  
 
    void DeflateRect(
    int 
    x ,  
    int 
    y) throw();
void DeflateRect(
    SIZE 
    size) throw();
void DeflateRect(
    LPCRECT 
    lpRect) throw();
void DeflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie le nombre d’unités à deflate gauche et droite du `CRect`.  
  
 *y*  
 Spécifie le nombre d’unités à deflate haut et bas de `CRect`.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) ou [CSize](../../atl-mfc-shared/reference/csize-class.md) qui spécifie le nombre d’unités à deflate `CRect`. Le `cx` valeur spécifie le nombre d’unités à compresser les côtés gauche et droit et `cy` valeur spécifie le nombre d’unités à deflate du haut et bas.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` qui spécifie le nombre d’unités à deflate de chaque côté.  
  
 *l*  
 Spécifie le nombre d’unités à deflate le côté gauche de `CRect`.  
  
 *t*  
 Spécifie le nombre d’unités à deflate haut de `CRect`.  
  
 *r*  
 Spécifie le nombre d’unités à deflate du côté droit de `CRect`.  
  
 *b*  
 Spécifie le nombre d’unités à deflate bas de `CRect`.  
  
### <a name="remarks"></a>Notes  
 Pour ce faire, `DeflateRect` ajoute des unités vers la gauche et le haut et soustrait unités à partir de la droite et en bas. Les paramètres de `DeflateRect` sont signés valeurs ; les valeurs positives deflate `CRect` et les valeurs négatives gonflé il.  
  
 Les deux premières surcharges deflate deux paires de côtés opposés du `CRect` afin que sa largeur totale est réduite par deux fois *x* (ou `cx`) et sa hauteur totale est réduite par deux fois *y* (ou `cy`). Les deux autres surcharges deflate chaque côté de `CRect` indépendamment des autres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#39](../../atl-mfc-shared/codesnippet/CPP/crect-class_5.cpp)]  
  
##  <a name="a-namecrectequalrecta-crectequalrect"></a><a name="crect__equalrect"></a>  CRect::EqualRect  
 Détermine si `CRect` est égal au rectangle donné.  
  
```  
 
BOOL EqualRect(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient les coordonnées du coin supérieur gauche et à droite d’un rectangle.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les deux rectangles ont le même haut, gauche, bas et valeurs ; sinon 0.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#40](../../atl-mfc-shared/codesnippet/CPP/crect-class_6.cpp)]  
  
##  <a name="a-namecrectheighta-crectheight"></a><a name="crect__height"></a>  CRect::Height  
 Calcule la hauteur de `CRect` en soustrayant la valeur de la valeur inférieure.  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La hauteur de `CRect`.  
  
### <a name="remarks"></a>Notes  
 La valeur résultante peut être négative.  
  
> [!NOTE]
>  Le rectangle doit être normalisé ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser le rectangle avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#41](../../atl-mfc-shared/codesnippet/CPP/crect-class_7.cpp)]  
  
##  <a name="a-namecrectinflaterecta-crectinflaterect"></a><a name="crect__inflaterect"></a>  CRect::InflateRect  
 `InflateRect` augmente `CRect` en déplaçant ses côtés en dehors de son centre.  
  
```  
 
    void InflateRect(
    int 
    x ,  
    int 
    y) throw();
void InflateRect(
    SIZE 
    size) throw();
void InflateRect(
    LPCRECT 
    lpRect) throw();
void InflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie le nombre d’unités pour l’augmentation de la gauche et droite du `CRect`.  
  
 *y*  
 Spécifie le nombre d’unités de valeur de l’augmentation du haut et bas de `CRect`.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) ou [CSize](../../atl-mfc-shared/reference/csize-class.md) qui spécifie le nombre d’unités augmentation `CRect`. Le `cx` valeur spécifie le nombre d’unités à augmenter les côtés gauche et droit et `cy` valeur spécifie le nombre d’unités à la valeur de l’augmentation du haut et bas.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` qui spécifie le nombre d’unités pour l’augmentation de chaque côté.  
  
 *l*  
 Spécifie le nombre d’unités pour l’augmentation de la partie gauche de `CRect`.  
  
 *t*  
 Spécifie le nombre d’unités pour l’augmentation de la partie supérieure de `CRect`.  
  
 *r*  
 Spécifie le nombre d’unités pour l’augmentation de la partie droite de `CRect`.  
  
 *b*  
 Spécifie le nombre d’unités pour l’augmentation de la partie inférieure de `CRect`.  
  
### <a name="remarks"></a>Notes  
 Pour ce faire, `InflateRect` soustrait des unités à partir de la gauche et le haut et ajoute des unités vers la droite et le bas. Les paramètres de `InflateRect` signé sont égales ; positif augmentation des valeurs `CRect` et les valeurs négatives deflate il.  
  
 Les deux premières surcharges gonflé les deux paires de côtés opposés du `CRect` afin que sa largeur totale est augmentée par deux fois *x* (ou `cx`) et sa hauteur totale est augmentée par deux fois *y* (ou `cy`). Les deux autres surcharges augmentation de chaque côté du `CRect` indépendamment des autres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#42](../../atl-mfc-shared/codesnippet/CPP/crect-class_8.cpp)]  
  
##  <a name="a-namecrectintersectrecta-crectintersectrect"></a><a name="crect__intersectrect"></a>  CRect::IntersectRect  
 Rend un `CRect` égal à l’intersection de deux rectangles existants.  
  
```  
 
    BOOL IntersectRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect1`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient un rectangle source.  
  
 `lpRect2`  
 Pointe vers une `RECT` structure ou `CRect` objet qui contient un rectangle source.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’intersection n’est pas vide. 0 si l’intersection est vide.  
  
### <a name="remarks"></a>Notes  
 L’intersection est le plus grand rectangle contenu dans les deux rectangles existants.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#43](../../atl-mfc-shared/codesnippet/CPP/crect-class_9.cpp)]  
  
##  <a name="a-namecrectisrectemptya-crectisrectempty"></a><a name="crect__isrectempty"></a>  CRect::IsRectEmpty  
 Détermine si `CRect` est vide.  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si `CRect` est vide ; 0 si `CRect` n’est pas vide.  
  
### <a name="remarks"></a>Notes  
 Un rectangle est vide si la largeur ou hauteur est 0 ou négatif. Diffère de `IsRectNull`, qui détermine si toutes les coordonnées du rectangle sont nuls.  
  
> [!NOTE]
>  Le rectangle doit être normalisé ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser le rectangle avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#44](../../atl-mfc-shared/codesnippet/CPP/crect-class_10.cpp)]  
  
##  <a name="a-namecrectisrectnulla-crectisrectnull"></a><a name="crect__isrectnull"></a>  CRect::IsRectNull  
 Détermine si le haut, gauche, bas et à droite des valeurs de `CRect` sont toujours égaux à 0.  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si `CRect`du haut, gauche, inférieure et valeurs sont tout égal à 0 ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Diffère de `IsRectEmpty`, qui détermine si le rectangle est vide.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#45](../../atl-mfc-shared/codesnippet/CPP/crect-class_11.cpp)]  
  
##  <a name="a-namecrectmovetoxa-crectmovetox"></a><a name="crect__movetox"></a>  CRect::MoveToX  
 Appelez cette fonction pour déplacer le rectangle à absolu coordonnée x spécifiée par *x*.  
  
```  
 
void MoveToX(
int   
x) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Coordonnée x absolue de l’angle supérieur gauche du rectangle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#46](../../atl-mfc-shared/codesnippet/CPP/crect-class_12.cpp)]  
  
##  <a name="a-namecrectmovetoxya-crectmovetoxy"></a><a name="crect__movetoxy"></a>  CRect::MoveToXY  
 Appelez cette fonction pour déplacer le rectangle pour l’absolu coordonnées x et y-spécifiée.  
  
```  
 
    void MoveToXY(
    int 
    x ,  
    int 
    y) throw();
void MoveToXY(
    POINT 
    point) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Coordonnée x absolue de l’angle supérieur gauche du rectangle.  
  
 *y*  
 Coordonnée y absolue de l’angle supérieur gauche du rectangle.  
  
 `point`  
 Un **POINT** structure qui spécifie l’angle supérieur gauche absolue du rectangle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#47](../../atl-mfc-shared/codesnippet/CPP/crect-class_13.cpp)]  
  
##  <a name="a-namecrectmovetoya-crectmovetoy"></a><a name="crect__movetoy"></a>  CRect::MoveToY  
 Appelez cette fonction pour déplacer le rectangle à la coordonnée absolue spécifiée par *y*.  
  
```  
 
void MoveToY(
int   
y) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *y*  
 Coordonnée y absolue de l’angle supérieur gauche du rectangle.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#48](../../atl-mfc-shared/codesnippet/CPP/crect-class_14.cpp)]  
  
##  <a name="a-namecrectnormalizerecta-crectnormalizerect"></a><a name="crect__normalizerect"></a>  CRect::NormalizeRect  
 Normalise `CRect` afin que la hauteur et la largeur sont positives.  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>Notes  
 Le rectangle est normalisé pour le positionnement de la quatrième quadrants, Windows utilise généralement pour les coordonnées. `NormalizeRect` Compare les valeurs supérieure et inférieure et permutation si le haut est supérieur à la partie inférieure. De même, il échange les valeurs de gauche et droit si gauche est supérieure à droite. Cette fonction est utile lorsque vous traitez des modes de mappage différent et inversé rectangles.  
  
> [!NOTE]
>  Les éléments suivants `CRect` fonctions membres exigent des rectangles normalisées afin de fonctionner correctement : [hauteur](#crect__height), [largeur](#crect__width), [taille](#crect__size), [IsRectEmpty](#crect__isrectempty), [PtInRect](#crect__ptinrect), [EqualRect](#crect__equalrect), [UnionRect](#crect__unionrect), [IntersectRect](#crect__intersectrect), [SubtractRect](#crect__subtractrect), [opérateur ==](#crect__operator__eq_eq), [opérateur ! =](#crect__operator__neq), [opérateur &#124 ;](#crect__operator__or), [opérateur &#124 ; =](#crect__operator__or_eq), [opérateur &](#crect__operator__amp_), et [opérateur & =](#crect__operator__amp__eq).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#49](../../atl-mfc-shared/codesnippet/CPP/crect-class_15.cpp)]  
  
##  <a name="a-namecrectoffsetrecta-crectoffsetrect"></a><a name="crect__offsetrect"></a>  CRect::OffsetRect  
 Déplace `CRect` par offsets spécifiés.  
  
```  
 
    void OffsetRect(
    int 
    x ,  
    int 
    y) throw();
void OffsetRect(
    POINT 
    point) throw();
void OffsetRect(
    SIZE 
    size) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie la quantité à déplacer vers la gauche ou la droite. Il doit être négatif pour le déplacer vers la gauche.  
  
 *y*  
 Spécifie la quantité à déplacer vers le haut ou vers le bas. Il doit être négatif pour le déplacer vers le haut.  
  
 `point`  
 Contient un [POINT](../../mfc/reference/point-structure1.md) structure ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet spécifiant les deux dimensions de déplacement.  
  
 `size`  
 Contient un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou [CSize](../../atl-mfc-shared/reference/csize-class.md) objet spécifiant les deux dimensions de déplacement.  
  
### <a name="remarks"></a>Notes  
 Déplace `CRect`*x* unités sur l’axe x et *y* unités sur l’axe des y. Le *x* et *y* paramètres sont donc les valeurs signées, `CRect` peut être déplacée vers la gauche ou la droite et vers le haut ou vers le bas.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#50](../../atl-mfc-shared/codesnippet/CPP/crect-class_16.cpp)]  
  
##  <a name="a-namecrectoperatorlpcrecta-crectoperator-lpcrect"></a><a name="crect__operator_lpcrect"></a>  CRect::operator LPCRECT  
 Convertit un `CRect` à un [LPCRECT](../../mfc/reference/data-types-mfc.md).  
  
''' opérateur LPCRECT() throw() d’appel const ;
```  
  
### Remarks  
 When you use this function, you don't need the address-of ( **&**) operator. This operator will be automatically used when you pass a `CRect` object to a function that expects an **LPCRECT**.  
  
### Example  
 [!code-cpp[NVC_ATLMFC_Utilities#58](../../atl-mfc-shared/codesnippet/CPP/crect-class_17.cpp)]  
  
##  <a name="crect__operator_lprect"></a>  CRect::operator LPRECT  
 Converts a `CRect` to an [LPRECT](../../mfc/reference/data-types-mfc.md).  
  
```  operator LPRECT() throw();
```  
  
### <a name="remarks"></a>Notes  
 Lorsque vous utilisez cette fonction, vous n’avez pas besoin adresses ( **&**) (opérateur). Cet opérateur est utilisé automatiquement lorsque vous passez un `CRect` objet à une fonction qui attend un `LPRECT`.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRect::operator LPCRECT](#crect__operator_lpcrect).  
  
##  <a name="a-namecrectoperatoreqa-crectoperator-"></a><a name="crect__operator__eq"></a>  CRect::operator =  
 Assigne *srcRect* à `CRect`.  
  
```  
 
void operator=(
const RECT& 
srcRect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *srcRect*  
 Fait référence à un rectangle source. Peut être un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#59](../../atl-mfc-shared/codesnippet/CPP/crect-class_18.cpp)]  
  
##  <a name="a-namecrectoperatoreqeqa-crectoperator-"></a><a name="crect__operator__eq_eq"></a>  CRect::operator ==  
 Détermine si `rect` est égal à `CRect` en comparant les coordonnées de leurs angles supérieur gauche et à droite.  
  
```  
 
BOOL operator==(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Fait référence à un rectangle source. Peut être un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro s’ils sont égaux ; sinon 0.  
  
### <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#60](../../atl-mfc-shared/codesnippet/CPP/crect-class_19.cpp)]  
  
##  <a name="a-namecrectoperatorneqa-crectoperator-"></a><a name="crect__operator__neq"></a>  CRect::operator ! =  
 Détermine si `rect` n’est pas égal à `CRect` en comparant les coordonnées de leurs angles supérieur gauche et à droite.  
  
```  
 
BOOL operator!=(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Fait référence à un rectangle source. Peut être un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si pas d’égalité ; sinon 0.  
  
### <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#61](../../atl-mfc-shared/codesnippet/CPP/crect-class_20.cpp)]  
  
##  <a name="a-namecrectoperatoraddeqa-crectoperator-"></a><a name="crect__operator__add_eq"></a>  CRect::operator +=  
 Déplacement les deux surcharges `CRect` par offsets spécifiés.  
  
```  
 
void operator+=(
POINT   
point) throw();

void operator+=(
SIZE   
size) throw();

void operator+=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Un [POINT](../../mfc/reference/point-structure1.md) structure ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui spécifie le nombre d’unités à déplacer le rectangle.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui spécifie le nombre d’unités à déplacer le rectangle.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient le nombre d’unités pour la valeur de chaque côté de l’augmentation `CRect`.  
  
### <a name="remarks"></a>Notes  
 Du paramètre *x* et *y* (ou `cx` et `cy`) valeurs sont ajoutées à `CRect`.  
  
 La troisième surcharge augmente `CRect` par le nombre spécifié d’unités de chaque membre du paramètre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#62](../../atl-mfc-shared/codesnippet/CPP/crect-class_21.cpp)]  
  
##  <a name="a-namecrectoperator-eqa-crectoperator--"></a><a name="crect__operator_-_eq"></a>  CRect::operator =  
 Déplacement les deux surcharges `CRect` par offsets spécifiés.  
  
```  
 
void operator-=(
POINT   
point) throw();

void operator-=(
SIZE   
size) throw();

void operator-=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Un [POINT](../../mfc/reference/point-structure1.md) structure ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui spécifie le nombre d’unités à déplacer le rectangle.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui spécifie le nombre d’unités à déplacer le rectangle.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient le nombre d’unités à deflate de chaque côté du `CRect`.  
  
### <a name="remarks"></a>Notes  
 Du paramètre *x* et *y* (ou `cx` et `cy`) valeurs sont soustraites de `CRect`.  
  
 La troisième surcharge réduit la forme `CRect` par le nombre spécifié d’unités de chaque membre du paramètre. Notez que cette surcharge fonctionne comme [DeflateRect](#crect__deflaterect).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#63](../../atl-mfc-shared/codesnippet/CPP/crect-class_22.cpp)]  
  
##  <a name="a-namecrectoperatorampeqa-crectoperator-amp"></a><a name="crect__operator__amp__eq"></a>  CRect::operator &amp;=  
 Jeux de `CRect` égal à l’intersection de `CRect` et `rect`.  
  
```  
 
void operator&=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Contient un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="remarks"></a>Notes  
 L’intersection est le plus grand rectangle est contenu dans les deux rectangles.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRect::IntersectRect](#crect__intersectrect).  
  
##  <a name="a-namecrectoperatororeqa-crectoperator-124"></a><a name="crect__operator__or_eq"></a>  CRect::operator &#124 ; =  
 Jeux de `CRect` égal à l’union de `CRect` et `rect`.  
  
```  
 
void operator|=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 Contient un `CRect` ou [RECT](../../mfc/reference/rect-structure1.md).  
  
### <a name="remarks"></a>Notes  
 L’union est le plus petit rectangle qui contient les deux rectangles source.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#64](../../atl-mfc-shared/codesnippet/CPP/crect-class_23.cpp)]  
  
##  <a name="a-namecrectoperatoradda-crectoperator-"></a><a name="crect__operator__add"></a>  CRect::operator +  
 Tout d’abord deux surcharges retournent un `CRect` objet est égal à `CRect` décalé par offsets spécifiés.  
  
```  
 
CRect operator+(
POINT   
point) const throw();

CRect operator+(
LPCRECT   
lpRect) const throw();

CRect operator+(
SIZE   
size) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Un [POINT](../../mfc/reference/point-structure1.md) structure ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui spécifie le nombre d’unités à déplacer la valeur de retour.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui spécifie le nombre d’unités à déplacer la valeur de retour.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient le nombre d’unités pour l’augmentation de chaque côté de la valeur de retour.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `CRect` résultant de déplacement ou gonfler `CRect` par le nombre d’unités spécifié dans le paramètre.  
  
### <a name="remarks"></a>Notes  
 Du paramètre *x* et *y* (ou `cx` et `cy`) les paramètres sont ajoutés à `CRect`de position.  
  
 La troisième surcharge retourne un nouveau `CRect` est égal à `CRect` augmenté le nombre spécifié d’unités de chaque membre du paramètre.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#65](../../atl-mfc-shared/codesnippet/CPP/crect-class_24.cpp)]  
  
##  <a name="a-namecrectoperator-a-crectoperator--"></a><a name="crect__operator_-"></a>  CRect::operator-  
 Tout d’abord deux surcharges retournent un `CRect` objet est égal à `CRect` décalé par offsets spécifiés.  
  
```  
 
CRect operator-(
POINT   
point) const throw();

CRect operator-(
SIZE   
size) const throw();

CRect operator-(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Un [POINT](../../mfc/reference/point-structure1.md) structure ou `CPoint` objet qui spécifie le nombre d’unités à déplacer la valeur de retour.  
  
 `size`  
 Un [TAILLE](http://msdn.microsoft.com/library/windows/desktop/dd145106) structure ou `CSize` objet qui spécifie le nombre d’unités à déplacer la valeur de retour.  
  
 `lpRect`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet qui contient le nombre d’unités à deflate de chaque côté de la valeur de retour.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `CRect` résultant de déplacement ou de DÉGONFLAGE `CRect` par le nombre d’unités spécifié dans le paramètre.  
  
### <a name="remarks"></a>Notes  
 Du paramètre *x* et *y* (ou `cx` et `cy`) sont soustraites paramètres `CRect`de position.  
  
 La troisième surcharge retourne un nouveau `CRect` est égal à `CRect` réduite par le nombre spécifié d’unités de chaque membre du paramètre. Notez que cette surcharge fonctionne comme [DeflateRect](#crect__deflaterect), et non pas [SubtractRect](#crect__subtractrect).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#66](../../atl-mfc-shared/codesnippet/CPP/crect-class_25.cpp)]  
  
##  <a name="a-namecrectoperatorampa-crectoperator-amp"></a><a name="crect__operator__amp_"></a>  CRect::operator &amp;  
 Retourne un `CRect` qui est l’intersection de `CRect` et *rect2*.  
  
```  
 
CRect operator&(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *rect2*  
 Contient un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CRect` qui est l’intersection de `CRect` et *rect2*.  
  
### <a name="remarks"></a>Notes  
 L’intersection est le plus grand rectangle est contenu dans les deux rectangles.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#67](../../atl-mfc-shared/codesnippet/CPP/crect-class_26.cpp)]  
  
##  <a name="a-namecrectoperatorora-crectoperator-124"></a><a name="crect__operator__or"></a>  CRect::operator &#124 ;  
 Retourne un `CRect` qui est l’union de `CRect` et *rect2*.  
  
```  
 
CRect operator|(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 *rect2*  
 Contient un [RECT](../../mfc/reference/rect-structure1.md) ou `CRect`.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CRect` qui est l’union de `CRect` et *rect2*.  
  
### <a name="remarks"></a>Notes  
 L’union est le plus petit rectangle qui contient les deux rectangles.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#68](../../atl-mfc-shared/codesnippet/CPP/crect-class_27.cpp)]  
  
##  <a name="a-namecrectptinrecta-crectptinrect"></a><a name="crect__ptinrect"></a>  CRect::PtInRect  
 Détermine si le point spécifié se trouve dans `CRect`.  
  
```  
 
BOOL PtInRect(
POINT   
point) const throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Contient un [POINT](../../mfc/reference/point-structure1.md) structure ou [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le point se trouve dans `CRect`; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Un point se trouve dans `CRect` si elle se trouve sur le côté gauche ou supérieur, soit dans les quatre côtés. Un point sur le côté droit ou inférieur est en dehors de `CRect`.  
  
> [!NOTE]
>  Le rectangle doit être normalisé ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser le rectangle avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#51](../../atl-mfc-shared/codesnippet/CPP/crect-class_28.cpp)]  
  
##  <a name="a-namecrectsetrecta-crectsetrect"></a><a name="crect__setrect"></a>  CRect::SetRect  
 Définit les dimensions de `CRect` vers les coordonnées spécifiées.  
  
```  
 
    void SetRect(
    int 
    x1 ,  
    int 
    y1 ,  
    int 
    x2 ,  
    int 
    y2) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `x1`  
 Spécifie la coordonnée x du coin supérieur gauche.  
  
 `y1`  
 Spécifie la coordonnée y du coin supérieur gauche.  
  
 `x2`  
 Spécifie la coordonnée x de l’angle inférieur droit.  
  
 `y2`  
 Spécifie la coordonnée y du coin inférieur droit.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#52](../../atl-mfc-shared/codesnippet/CPP/crect-class_29.cpp)]  
  
##  <a name="a-namecrectsetrectemptya-crectsetrectempty"></a><a name="crect__setrectempty"></a>  CRect::SetRectEmpty  
 Permet de `CRect` un rectangle null en définissant toutes les coordonnées à zéro.  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#53](../../atl-mfc-shared/codesnippet/CPP/crect-class_30.cpp)]  
  
##  <a name="a-namecrectsizea-crectsize"></a><a name="crect__size"></a>  CRect::Size  
 Le `cx` et `cy` contiennent des membres de la valeur de retour la hauteur et la largeur de `CRect`.  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un [CSize](../../atl-mfc-shared/reference/csize-class.md) objet qui contient la taille de `CRect`.  
  
### <a name="remarks"></a>Notes  
 La hauteur ou la largeur peut être négatif.  
  
> [!NOTE]
>  Le rectangle doit être normalisé ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser le rectangle avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#54](../../atl-mfc-shared/codesnippet/CPP/crect-class_31.cpp)]  
  
##  <a name="a-namecrectsubtractrecta-crectsubtractrect"></a><a name="crect__subtractrect"></a>  CRect::SubtractRect  
 Rend les dimensions de la **CRect** égale à la soustraction de `lpRectSrc2` de `lpRectSrc1`.  
  
```  
 
    BOOL SubtractRect(
    LPCRECT 
    lpRectSrc1 ,  
    LPCRECT 
    lpRectSrc2) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRectSrc1`  
 Pointe vers le [RECT](../../mfc/reference/rect-structure1.md) structure ou `CRect` objet à partir duquel un rectangle à soustraire.  
  
 `lpRectSrc2`  
 Pointe vers le `RECT` structure ou `CRect` objet à soustraire du rectangle vers lequel pointe le `lpRectSrc1` paramètre.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La soustraction est le plus petit rectangle qui contient tous les points de `lpRectScr1` qui ne sont pas à l’intersection entre `lpRectScr1` et *lpRectScr2*.  
  
 Le rectangle spécifié par `lpRectSrc1` est inchangée si le rectangle spécifié par `lpRectSrc2` ne se chevauchent pas complètement le rectangle spécifié par *lpRectSrc1* dans au moins un de la direction x ou y.  
  
 Par exemple, si `lpRectSrc1` était (10,10, 100,100) et `lpRectSrc2` ont été (50,50, 150,150), le rectangle indiqué par `lpRectSrc1` il reste inchangé lorsque la fonction a renvoyé. Si `lpRectSrc1` étaient (10,10, 100,100) et `lpRectSrc2` ont été (50,10, 150,150), toutefois, le rectangle indiqué par `lpRectSrc1` contient les coordonnées (10,10, 50,100) lorsque la fonction a renvoyé.  
  
 `SubtractRect` n’est pas le même que [opérateur -](#crect__operator_-) ni [opérateur-=](#crect__operator_-_eq). Aucun de ces opérateurs n’appelle jamais `SubtractRect`.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#55](../../atl-mfc-shared/codesnippet/CPP/crect-class_32.cpp)]  
  
##  <a name="a-namecrecttoplefta-crecttopleft"></a><a name="crect__topleft"></a>  CRect::TopLeft  
 Les coordonnées sont retournées comme une référence à un [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) objet qui est contenue dans `CRect`.  
  
```  
 
CPoint& TopLeft() throw();

const CPoint& TopLeft() const throw();

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les coordonnées de l’angle supérieur gauche du rectangle.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez utiliser cette fonction pour obtenir ou définir l’angle supérieur gauche du rectangle. Définir l’angle à l’aide de cette fonction sur le côté gauche de l’opérateur d’assignation.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CRect::CenterPoint](#crect__centerpoint).  
  
##  <a name="a-namecrectunionrecta-crectunionrect"></a><a name="crect__unionrect"></a>  CRect::UnionRect  
 Rend les dimensions de `CRect` égal à l’union de rectangles deux sources.  
  
```  
 
    BOOL UnionRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect1`  
 Pointe vers une [RECT](../../mfc/reference/rect-structure1.md) ou `CRect` qui contient un rectangle source.  
  
 `lpRect2`  
 Pointe vers un `RECT` ou `CRect` qui contient un rectangle source.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’union n’est pas vide. 0 si l’union est vide.  
  
### <a name="remarks"></a>Notes  
 L’union est le plus petit rectangle qui contient les deux rectangles source.  
  
 Windows ignore les dimensions du rectangle vide ; Autrement dit, un rectangle qui n’a aucune hauteur ou aucune largeur.  
  
> [!NOTE]
>  Les rectangles doivent être normalisées ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser les rectangles avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#56](../../atl-mfc-shared/codesnippet/CPP/crect-class_33.cpp)]  
  
##  <a name="a-namecrectwidtha-crectwidth"></a><a name="crect__width"></a>  CRect::Width  
 Calcule la largeur de `CRect` en soustrayant la valeur de gauche de la valeur appropriée.  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La largeur de `CRect`.  
  
### <a name="remarks"></a>Notes  
 La largeur peut être négative.  
  
> [!NOTE]
>  Le rectangle doit être normalisé ou cette fonction peut échouer. Vous pouvez appeler [NormalizeRect](#crect__normalizerect) pour normaliser le rectangle avant d’appeler cette fonction.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATLMFC_Utilities#57](../../atl-mfc-shared/codesnippet/CPP/crect-class_34.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CPoint (classe)](../../atl-mfc-shared/reference/cpoint-class.md)   
 [CSize (classe)](../../atl-mfc-shared/reference/csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)

