---
title: CRgn (classe) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRgn
- AFXWIN/CRgn
- AFXWIN/CRgn::CRgn
- AFXWIN/CRgn::CombineRgn
- AFXWIN/CRgn::CopyRgn
- AFXWIN/CRgn::CreateEllipticRgn
- AFXWIN/CRgn::CreateEllipticRgnIndirect
- AFXWIN/CRgn::CreateFromData
- AFXWIN/CRgn::CreateFromPath
- AFXWIN/CRgn::CreatePolygonRgn
- AFXWIN/CRgn::CreatePolyPolygonRgn
- AFXWIN/CRgn::CreateRectRgn
- AFXWIN/CRgn::CreateRectRgnIndirect
- AFXWIN/CRgn::CreateRoundRectRgn
- AFXWIN/CRgn::EqualRgn
- AFXWIN/CRgn::FromHandle
- AFXWIN/CRgn::GetRegionData
- AFXWIN/CRgn::GetRgnBox
- AFXWIN/CRgn::OffsetRgn
- AFXWIN/CRgn::PtInRegion
- AFXWIN/CRgn::RectInRegion
- AFXWIN/CRgn::SetRectRgn
dev_langs:
- C++
helpviewer_keywords:
- CRgn [MFC], CRgn
- CRgn [MFC], CombineRgn
- CRgn [MFC], CopyRgn
- CRgn [MFC], CreateEllipticRgn
- CRgn [MFC], CreateEllipticRgnIndirect
- CRgn [MFC], CreateFromData
- CRgn [MFC], CreateFromPath
- CRgn [MFC], CreatePolygonRgn
- CRgn [MFC], CreatePolyPolygonRgn
- CRgn [MFC], CreateRectRgn
- CRgn [MFC], CreateRectRgnIndirect
- CRgn [MFC], CreateRoundRectRgn
- CRgn [MFC], EqualRgn
- CRgn [MFC], FromHandle
- CRgn [MFC], GetRegionData
- CRgn [MFC], GetRgnBox
- CRgn [MFC], OffsetRgn
- CRgn [MFC], PtInRegion
- CRgn [MFC], RectInRegion
- CRgn [MFC], SetRectRgn
ms.assetid: d904da84-76aa-481e-8780-b09485f49e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b569efb201f95ade8987aaa89bb6cea1bc0c15c1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="crgn-class"></a>CRgn (classe)
Encapsule une région GDI (Graphics Device Interface) Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRgn : public CGdiObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRgn::CRgn](#crgn)|Construit un objet `CRgn`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRgn::CombineRgn](#combinergn)|Définit un `CRgn` afin qu’elle soit équivalente à l’union de deux spécifié de l’objet `CRgn` objets.|  
|[CRgn::CopyRgn](#copyrgn)|Définit un `CRgn` afin qu’il soit une copie d’un élément spécifié de l’objet `CRgn` objet.|  
|[CRgn::CreateEllipticRgn](#createellipticrgn)|Initialise un `CRgn` objet avec une zone elliptique.|  
|[CRgn::CreateEllipticRgnIndirect](#createellipticrgnindirect)|Initialise un `CRgn` objet avec une région en forme d’ellipse définie par un [RECT](../../mfc/reference/rect-structure1.md) structure.|  
|[CRgn::CreateFromData](#createfromdata)|Crée une région à partir de la région et la transformation donnée.|  
|[CRgn::CreateFromPath](#createfrompath)|Crée une région à partir du chemin qui est sélectionné dans le contexte de périphérique donné.|  
|[CRgn::CreatePolygonRgn](#createpolygonrgn)|Initialise un `CRgn` objet avec une zone polygonale. Le système ferme le polygone automatiquement, si nécessaire, en dessinant une ligne à partir du dernier sommet au premier.|  
|[CRgn::CreatePolyPolygonRgn](#createpolypolygonrgn)|Initialise un `CRgn` objet avec une zone composée d’une série de polygones fermés. Les polygones peuvent être disjoints ou ils peuvent se chevaucher.|  
|[CRgn::CreateRectRgn](#createrectrgn)|Initialise un `CRgn` objet avec une zone rectangulaire.|  
|[CRgn::CreateRectRgnIndirect](#createrectrgnindirect)|Initialise un `CRgn` objet avec une zone rectangulaire définie par un [RECT](../../mfc/reference/rect-structure1.md) structure.|  
|[CRgn::CreateRoundRectRgn](#createroundrectrgn)|Initialise un `CRgn` objet avec une zone rectangulaire à coins arrondis.|  
|[CRgn::EqualRgn](#equalrgn)|Vérifie deux `CRgn` objets afin de déterminer s’ils sont équivalents.|  
|[CRgn::FromHandle](#fromhandle)|Retourne un pointeur vers un `CRgn` lorsqu’un handle vers une région Windows de l’objet.|  
|[CRgn::GetRegionData](#getregiondata)|Remplit la mémoire tampon spécifiée avec les données qui décrivent la région donnée.|  
|[CRgn::GetRgnBox](#getrgnbox)|Récupère les coordonnées du rectangle englobant d’un `CRgn` objet.|  
|[CRgn::OffsetRgn](#offsetrgn)|Déplace un `CRgn` objet par le décalage spécifiés.|  
|[CRgn::PtInRegion](#ptinregion)|Détermine si un point spécifié est dans la région.|  
|[CRgn::RectInRegion](#rectinregion)|Détermine si une partie d’un rectangle spécifié est dans les limites de la région.|  
|[CRgn::SetRectRgn](#setrectrgn)|Définit le `CRgn` objet dans la région rectangulaire spécifiée.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRgn::operator HRGN](#operator_hrgn)|Retourne le handle Windows contenu dans le `CRgn` objet.|  
  
## <a name="remarks"></a>Notes  
 Une région est une zone elliptique ou polygonale dans une fenêtre. Pour utiliser les régions, vous utilisez les fonctions membres de classe `CRgn` avec les fonctions de découpage définies en tant que membres de classe `CDC`.  
  
 Les fonctions membres de `CRgn` créer, modifier et récupérer des informations sur l’objet de région pour lequel elles sont appelées.  
  
 Pour plus d’informations sur l’utilisation de `CRgn`, consultez [objets graphiques](../../mfc/graphic-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CRgn`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="combinergn"></a>  CRgn::CombineRgn  
 Crée une nouvelle région GDI en combinant les deux régions existantes.  
  
```  
int CombineRgn(
    CRgn* pRgn1,  
    CRgn* pRgn2,  
    int nCombineMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRgn1`  
 Identifie une zone existante.  
  
 `pRgn2`  
 Identifie une zone existante.  
  
 `nCombineMode`  
 Spécifie l’opération à effectuer lors de la combinaison des régions de deux sources. Il peut prendre l’une des valeurs suivantes :  
  
- **RGN_AND** utilise des zones se chevauchant de deux régions (intersection).  
  
- **RGN_COPY** crée une copie de la région 1 (identifié par `pRgn1`).  
  
- **RGN_DIFF** crée une zone composée des zones de région 1 (identifié par `pRgn1`) qui ne sont pas partie de la région 2 (identifié par `pRgn2`).  
  
- **RGN_OR** combine les deux régions dans leur intégralité (union).  
  
- **RGN_XOR** combine les deux régions, mais supprime les zones qui se chevauchent.  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie le type de la région qui en résulte. Il peut prendre l’une des valeurs suivantes :  
  
- **COMPLEXREGION** nouvelle région a chevauchement des bordures.  
  
- **ERREUR** aucune région nouveau créé.  
  
- **NULLREGION** nouvelle zone est vide.  
  
- **SIMPLEREGION** nouvelle région n’a aucune bordure qui se chevauchent.  
  
### <a name="remarks"></a>Notes  
 Les régions sont combinées comme spécifié par `nCombineMode`.  
  
 Les deux spécifiés régions sont combinées, et le handle obtenu de la région est stocké dans le `CRgn` objet. Par conséquent, quelle que soit la région est stockée dans le `CRgn` objet est remplacé par la région combinée.  
  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Utilisez [CopyRgn](#copyrgn) simplement copier une région dans une autre région.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#144](../../mfc/codesnippet/cpp/crgn-class_1.cpp)]  
  
##  <a name="copyrgn"></a>  CRgn::CopyRgn  
 Copie la région définie par `pRgnSrc` dans le `CRgn` objet.  
  
```  
int CopyRgn(CRgn* pRgnSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRgnSrc`  
 Identifie une zone existante.  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie le type de la région qui en résulte. Il peut prendre l’une des valeurs suivantes :  
  
- **COMPLEXREGION** nouvelle région a chevauchement des bordures.  
  
- **ERREUR** aucune région nouveau créé.  
  
- **NULLREGION** nouvelle zone est vide.  
  
- **SIMPLEREGION** nouvelle région n’a aucune bordure qui se chevauchent.  
  
### <a name="remarks"></a>Notes  
 La nouvelle région remplace la région précédemment stockée dans les `CRgn` objet. Cette fonction est un cas spécial de la [CombineRgn](#combinergn) fonction membre.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="createellipticrgn"></a>  CRgn::CreateEllipticRgn  
 Crée une zone elliptique.  
  
```  
BOOL CreateEllipticRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Paramètres  
 `x1`  
 Spécifie la coordonnée x logique de l’angle supérieur gauche du rectangle englobant de l’ellipse.  
  
 `y1`  
 Spécifie la coordonnée y logique de l’angle supérieur gauche du rectangle englobant de l’ellipse.  
  
 `x2`  
 Spécifie la coordonnée x logique de l’angle inférieur droit du rectangle englobant de l’ellipse.  
  
 `y2`  
 Spécifie la coordonnée y logique de l’angle inférieur droit du rectangle englobant de l’ellipse.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La région est définie par le rectangle englobant spécifié par `x1`, `y1`, `x2`, et `y2`. La région est stockée dans le `CRgn` objet.  
  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Après avoir terminé à l’aide d’une région créée avec le `CreateEllipticRgn` (fonction), une application doit sélectionner la région hors du contexte de périphérique et utilisez le `DeleteObject` afin de le supprimer.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#145](../../mfc/codesnippet/cpp/crgn-class_2.cpp)]  
  
##  <a name="createellipticrgnindirect"></a>  CRgn::CreateEllipticRgnIndirect  
 Crée une zone elliptique.  
  
```  
BOOL CreateEllipticRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers un `RECT` structure ou un `CRect` objet qui contient les coordonnées logiques des angles supérieur gauche et inférieur droit du rectangle englobant de l’ellipse.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La région est définie par la structure ou l’objet vers lequel pointé `lpRect` et est stocké dans le `CRgn` objet.  
  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Après avoir terminé à l’aide d’une région créée avec le `CreateEllipticRgnIndirect` (fonction), une application doit sélectionner la région hors du contexte de périphérique et utilisez le `DeleteObject` afin de le supprimer.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRgn::CreateRectRgnIndirect](#createrectrgnindirect).  
  
##  <a name="createfromdata"></a>  CRgn::CreateFromData  
 Crée une région à partir de la région et la transformation donnée.  
  
```  
BOOL CreateFromData(
    const XFORM* lpXForm,  
    int nCount,  
    const RGNDATA* pRgnData);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpXForm*  
 Pointe vers une [XFORM](../../mfc/reference/xform-structure.md) structure de données qui définit la transformation à exécuter sur la région. Si ce pointeur est **NULL**, la transformation d’identité est utilisée.  
  
 `nCount`  
 Spécifie le nombre d’octets indiqué par `pRgnData`.  
  
 `pRgnData`  
 Pointe vers un [RGNDATA](../../mfc/reference/rgndata-structure.md) structure de données qui contient les données de la région.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Une application peut récupérer des données d’une région en appelant le `CRgn::GetRegionData` (fonction).  
  
##  <a name="createfrompath"></a>  CRgn::CreateFromPath  
 Crée une région à partir du chemin qui est sélectionné dans le contexte de périphérique donné.  
  
```  
BOOL CreateFromPath(CDC* pDC);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Identifie un contexte de périphérique qui contient un chemin d’accès fermé.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur différente de zéro si la fonction réussit ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le contexte de périphérique identifié par le `pDC` paramètre doit contenir un chemin d’accès fermé. Après avoir `CreateFromPath` convertit un chemin d’accès dans une région, Windows ignore le chemin d’accès fermé à partir du contexte de périphérique.  
  
##  <a name="createpolygonrgn"></a>  CRgn::CreatePolygonRgn  
 Crée une zone polygonale.  
  
```  
BOOL CreatePolygonRgn(
    LPPOINT lpPoints,  
    int nCount,  
    int nMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPoints`  
 Pointe vers un tableau de **POINT** structures ou un tableau de `CPoint` objets. Chaque structure spécifie la coordonnée x et la coordonnée y d’un sommet du polygone. Le **POINT** structure a la forme suivante :  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `nCount`  
 Spécifie le nombre de **POINT** structures ou `CPoint` objets dans le tableau vers lequel pointe `lpPoints`.  
  
 `nMode`  
 Spécifie le mode de remplissage de la région. Ce paramètre peut être soit **autre** ou **enroulement**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Le système ferme le polygone automatiquement, si nécessaire, en dessinant une ligne à partir du dernier sommet au premier. La région qui en résulte est stockée dans le `CRgn` objet.  
  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Lorsque le mode de remplissage de polygone est **autre**, le système remplit la zone entre les côtés d’un polygone impaires et paires sur chaque ligne d’analyse. Autrement dit, le système remplit la zone entre le premier et deuxième côté, entre les troisième et quatrième côté et ainsi de suite.  
  
 Lorsque le mode de remplissage de polygone est **enroulement**, le système utilise la direction dans laquelle figure a été dessinée pour déterminer s’il faut remplir une zone. Chaque segment de ligne dans un polygone est dessiné dans un dans le sens horaire ou aiguilles. Chaque fois qu’une ligne imaginaire dessinée à partir d’une zone entre parenthèses à l’extérieur d’une figure traverse un segment de ligne dans le sens horaire, c’est un nombre qui est incrémenté. Lorsque la ligne traverse un segment de ligne dans le sens inverse, le nombre est décrémenté. La zone est remplie si le nombre est différente de zéro lorsque la ligne atteint à l’extérieur de la figure.  
  
 Lorsqu’une application a terminé d’utiliser une région créée avec le `CreatePolygonRgn` (fonction), il doit sélectionner la région hors du contexte de périphérique et utilisez le `DeleteObject` fonction à supprimer.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#146](../../mfc/codesnippet/cpp/crgn-class_3.cpp)]  
  
##  <a name="createpolypolygonrgn"></a>  CRgn::CreatePolyPolygonRgn  
 Crée une zone composée d’une série de polygones fermés.  
  
```  
BOOL CreatePolyPolygonRgn(
    LPPOINT lpPoints,  
    LPINT lpPolyCounts,  
    int nCount,  
    int nPolyFillMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpPoints`  
 Pointe vers un tableau de **POINT** structures ou un tableau de `CPoint` les objets qui définit les sommets du polygone. Chaque polygone doit être explicitement fermé, car le système ne les ferme pas automatiquement. Les polygones sont spécifiés consécutifs. Le **POINT** structure a la forme suivante :  
  
 `typedef struct tagPOINT {`  
  
 `int x;`  
  
 `int y;`  
  
 `} POINT;`  
  
 `lpPolyCounts`  
 Pointe vers un tableau d’entiers. Le premier entier spécifie le nombre de sommets dans la première polygone dans le `lpPoints` tableau, le second entier spécifie le nombre de sommets dans le deuxième polygone et ainsi de suite.  
  
 `nCount`  
 Spécifie le nombre total de nombres entiers dans le `lpPolyCounts` tableau.  
  
 `nPolyFillMode`  
 Spécifie le mode de remplissage de polygones. Cette valeur peut être soit **autre** ou **enroulement**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La région qui en résulte est stockée dans le `CRgn` objet.  
  
 Les polygones peuvent être disjoints ou ils peuvent se chevaucher.  
  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Lorsque le mode de remplissage de polygone est **autre**, le système remplit la zone entre les côtés d’un polygone impaires et paires sur chaque ligne d’analyse. Autrement dit, le système remplit la zone entre le premier et deuxième côté, entre les troisième et quatrième côté et ainsi de suite.  
  
 Lorsque le mode de remplissage de polygone est **enroulement**, le système utilise la direction dans laquelle figure a été dessinée pour déterminer s’il faut remplir une zone. Chaque segment de ligne dans un polygone est dessiné dans un dans le sens horaire ou aiguilles. Chaque fois qu’une ligne imaginaire dessinée à partir d’une zone entre parenthèses à l’extérieur d’une figure traverse un segment de ligne dans le sens horaire, c’est un nombre qui est incrémenté. Lorsque la ligne traverse un segment de ligne dans le sens inverse, le nombre est décrémenté. La zone est remplie si le nombre est différente de zéro lorsque la ligne atteint à l’extérieur de la figure.  
  
 Lorsqu’une application a terminé d’utiliser une région créée avec le `CreatePolyPolygonRgn` (fonction), il doit sélectionner la région hors du contexte de périphérique et utilisez le [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) fonction membre à supprimer.  
  
##  <a name="createrectrgn"></a>  CRgn::CreateRectRgn  
 Crée une zone rectangulaire qui est stockée dans le `CRgn` objet.  
  
```  
BOOL CreateRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);
```  
  
### <a name="parameters"></a>Paramètres  
 `x1`  
 Spécifie la coordonnée x logique de l’angle supérieur gauche de la région.  
  
 `y1`  
 Spécifie la coordonnée y logique de l’angle supérieur gauche de la région.  
  
 `x2`  
 Spécifie la coordonnée x logique de l’angle inférieur droit de la région.  
  
 `y2`  
 Spécifie la coordonnée y logique de l’angle inférieur droit de la région.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Après avoir terminé à l’aide d’une région créée par `CreateRectRgn`, une application doit utiliser le [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) fonction membre à supprimer de la région.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#147](../../mfc/codesnippet/cpp/crgn-class_4.cpp)]  
  
 Pour obtenir un exemple supplémentaire, consultez [CRgn::CombineRgn](#combinergn).  
  
##  <a name="createrectrgnindirect"></a>  CRgn::CreateRectRgnIndirect  
 Crée une zone rectangulaire qui est stockée dans le `CRgn` objet.  
  
```  
BOOL CreateRectRgnIndirect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers un `RECT` structure ou `CRect` objet qui contient les coordonnées logiques des angles supérieur gauche et à droite de la région. Le `RECT` structure a la forme suivante :  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Après avoir terminé à l’aide d’une région créée par `CreateRectRgnIndirect`, une application doit utiliser le [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) fonction membre à supprimer de la région.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#148](../../mfc/codesnippet/cpp/crgn-class_5.cpp)]  
  
##  <a name="createroundrectrgn"></a>  CRgn::CreateRoundRectRgn  
 Crée une zone rectangulaire à coins arrondis qui est stocké dans le `CRgn` objet.  
  
```  
BOOL CreateRoundRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2,  
    int x3,  
    int y3);
```  
  
### <a name="parameters"></a>Paramètres  
 `x1`  
 Spécifie la coordonnée x logique de l’angle supérieur gauche de la région.  
  
 `y1`  
 Spécifie la coordonnée y logique de l’angle supérieur gauche de la région.  
  
 `x2`  
 Spécifie la coordonnée x logique de l’angle inférieur droit de la région.  
  
 `y2`  
 Spécifie la coordonnée y logique de l’angle inférieur droit de la région.  
  
 *x3*  
 Spécifie la largeur de l’ellipse utilisée pour créer les angles arrondis.  
  
 `y3`  
 Spécifie la hauteur de l’ellipse utilisée pour créer les angles arrondis.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’opération a réussi ; Sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La taille d’une région est limitée à 32 767 par 32 767 des unités logiques ou de 64 Ko de mémoire, la plus petite étant retenue.  
  
 Lorsqu’une application a terminé d’utiliser une région créée avec le `CreateRoundRectRgn` (fonction), il doit sélectionner la région hors du contexte de périphérique et utilisez le [CGDIObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) fonction membre à supprimer.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#149](../../mfc/codesnippet/cpp/crgn-class_6.cpp)]  
  
##  <a name="crgn"></a>  CRgn::CRgn  
 Construit un objet `CRgn`.  
  
```  
CRgn();
```  
  
### <a name="remarks"></a>Notes  
 Le `m_hObject` membre de données ne contient pas une région GDI Windows valide jusqu'à ce que l’objet est initialisé avec un ou plusieurs des autres `CRgn` fonctions membres.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRgn::CreateRoundRectRgn](#createroundrectrgn).  
  
##  <a name="equalrgn"></a>  CRgn::EqualRgn  
 Détermine si la région donnée est équivalente à la région stockée dans le `CRgn` objet.  
  
```  
BOOL EqualRgn(CRgn* pRgn) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pRgn`  
 Identifie une zone.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les deux régions sont équivalentes ; Sinon, 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView#150](../../mfc/codesnippet/cpp/crgn-class_7.cpp)]  
  
##  <a name="fromhandle"></a>  CRgn::FromHandle  
 Retourne un pointeur vers un `CRgn` lorsqu’un handle vers une région Windows de l’objet.  
  
```  
static CRgn* PASCAL FromHandle(HRGN hRgn);
```  
  
### <a name="parameters"></a>Paramètres  
 `hRgn`  
 Spécifie un handle à une région de Windows.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers un `CRgn` objet. Si la fonction n’a pas réussie, la valeur de retour est **NULL**.  
  
### <a name="remarks"></a>Notes  
 Si un `CRgn` objet n’est pas déjà attaché au handle, un fichier temporaire `CRgn` objet est créé et attaché. Ce fichier temporaire `CRgn` objet est valide uniquement jusqu'à ce que la prochaine fois que l’application possède des temps d’inactivité dans la boucle d’événements, alors graphique temporaire tous les objets sont supprimés. Une autre façon d’autres termes est que l’objet temporaire est valide uniquement lors du traitement du message d’une fenêtre.  
  
##  <a name="getregiondata"></a>  CRgn::GetRegionData  
 Remplit la mémoire tampon spécifiée qui décrit la région de données.  
  
```  
int GetRegionData(
    LPRGNDATA lpRgnData,  
    int nCount) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRgnData`  
 Pointe vers un [RGNDATA](../../mfc/reference/rgndata-structure.md) structure de données qui reçoit les informations. Si ce paramètre est **NULL**, la valeur de retour contient le nombre d’octets nécessaires pour les données de la région.  
  
 `nCount`  
 Spécifie la taille, en octets, de la `lpRgnData` mémoire tampon.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit et `nCount` spécifie un nombre suffisant d’octets, la valeur de retour est toujours `nCount`. Si la fonction échoue, ou si `nCount` spécifie inférieur à un nombre suffisant d’octets, la valeur de retour est 0 (erreur).  
  
### <a name="remarks"></a>Notes  
 Ces données incluent les dimensions des rectangles qui composent la région. Cette fonction est utilisée conjointement avec la `CRgn::CreateFromData` (fonction).  
  
##  <a name="getrgnbox"></a>  CRgn::GetRgnBox  
 Récupère les coordonnées du rectangle englobant de le `CRgn` objet.  
  
```  
int GetRgnBox(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers un `RECT` structure ou `CRect` objet pour recevoir les coordonnées du rectangle englobant. Le `RECT` structure a la forme suivante :  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie le type de la région. Il peut être une des valeurs suivantes :  
  
- **COMPLEXREGION** région a chevauchement des bordures.  
  
- **NULLREGION** région est vide.  
  
- **ERREUR** `CRgn` objet ne spécifie pas une région valide.  
  
- **SIMPLEREGION** région ne possède pas de bordure qui se chevauchent.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRgn::CreatePolygonRgn](#createpolygonrgn).  
  
##  <a name="offsetrgn"></a>  CRgn::OffsetRgn  
 Déplace la région stockée dans le `CRgn` objet par le décalage spécifiés.  
  
```  
int OffsetRgn(
    int x,  
    int y);  
  
int OffsetRgn(POINT point);
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie le nombre d’unités à déplacer vers la gauche ou droite.  
  
 *y*  
 Spécifie le nombre d’unités à déplacer vers le haut ou vers le bas.  
  
 `point`  
 La coordonnée x de `point` Spécifie le nombre d’unités à déplacer vers la gauche ou droite. Coordonnée y de `point` Spécifie le nombre d’unités à déplacer vers le haut ou vers le bas. Le `point` paramètre peut être soit un **POINT** structure ou un `CPoint` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Type de la nouvelle région. Il peut prendre l’une des valeurs suivantes :  
  
- **COMPLEXREGION** région a chevauchement des bordures.  
  
- **ERREUR** descripteur de région n’est pas valide.  
  
- **NULLREGION** région est vide.  
  
- **SIMPLEREGION** région ne possède pas de bordure qui se chevauchent.  
  
### <a name="remarks"></a>Notes  
 La fonction déplace la région *x* unités sur l’axe x et *y* unités sur l’axe y.  
  
 Les valeurs des coordonnées d’une région doivent être inférieure ou égale à 32 767 et supérieure ou égale à-32 768. Le *x* et *y* paramètres doivent être choisies avec soin pour éviter les coordonnées de la région non valide.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CRgn::CreateEllipticRgn](#createellipticrgn).  
  
##  <a name="operator_hrgn"></a>  CRgn::operator HRGN  
 Utilisez cet opérateur pour obtenir le handle Windows GDI joint de le `CRgn` objet.  
  
```  
operator HRGN() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si réussie, un handle vers l’objet GDI Windows représenté par le `CRgn` de l’objet ; sinon **NULL**.  
  
### <a name="remarks"></a>Notes  
 Cet opérateur est un opérateur de cast, qui prend en charge l’utilisation directe d’une **HRGN** objet.  
  
 Pour plus d’informations sur l’utilisation des objets graphiques, consultez l’article [graphique objets](http://msdn.microsoft.com/library/windows/desktop/dd144962) dans le Kit de développement logiciel Windows.  
  
##  <a name="ptinregion"></a>  CRgn::PtInRegion  
 Vérifie si le point de données par *x* et *y* dans la région stockée dans le `CRgn` objet.  
  
```  
BOOL PtInRegion(
    int x,  
    int y) const;  
  
BOOL PtInRegion(POINT point) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *x*  
 Spécifie la coordonnée x logique du point à tester.  
  
 *y*  
 Spécifie la coordonnée y logique du point à tester.  
  
 `point`  
 Les coordonnées x et y de `point` spécifier les coordonnées x et y du point à tester la valeur de. Le `point` paramètre peut être un **POINT** structure ou un `CPoint` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le point se trouve dans la région ; Sinon, 0.  
  
##  <a name="rectinregion"></a>  CRgn::RectInRegion  
 Détermine si une partie du rectangle spécifié par `lpRect` est dans les limites de la région stockées dans le `CRgn` objet.  
  
```  
BOOL RectInRegion(LPCRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers un `RECT` structure ou `CRect` objet. Le `RECT` structure a la forme suivante :  
  
 `typedef struct tagRECT {`  
  
 `int left;`  
  
 `int top;`  
  
 `int right;`  
  
 `int bottom;`  
  
 `} RECT;`  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si n’importe quelle partie du rectangle spécifié se situe dans les limites de la région ; Sinon, 0.  
  
##  <a name="setrectrgn"></a>  CRgn::SetRectRgn  
 Crée une zone rectangulaire.  
  
```  
void SetRectRgn(
    int x1,  
    int y1,  
    int x2,  
    int y2);  
  
void SetRectRgn(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `x1`  
 Spécifie la coordonnée x de l’angle supérieur gauche de la zone rectangulaire.  
  
 `y1`  
 Spécifie la coordonnée y de l’angle supérieur gauche de la zone rectangulaire.  
  
 `x2`  
 Spécifie la coordonnée x de l’angle inférieur droit de la zone rectangulaire.  
  
 `y2`  
 Spécifie la coordonnée y de l’angle inférieur droit de la zone rectangulaire.  
  
 `lpRect`  
 Spécifie la région rectangulaire. Peut être soit un pointeur vers un `RECT` structure ou un `CRect` objet.  
  
### <a name="remarks"></a>Notes  
 Contrairement aux [CreateRectRgn](#createrectrgn), toutefois, il n’alloue pas de mémoire supplémentaire à partir du tas d’application Windows local. En revanche, il utilise l’espace alloué pour la région est stockée dans le `CRgn` objet. Cela signifie que la `CRgn` objet doit déjà être initialisé avec une région Windows valide avant d’appeler `SetRectRgn`. Les points de données par `x1`, `y1`, `x2`, et `y2` spécifier la taille minimale de l’espace alloué.  
  
 Utilisez cette fonction au lieu du `CreateRectRgn` fonction membre afin d’éviter les appels au Gestionnaire de mémoire locale.  
  
## <a name="see-also"></a>Voir aussi  
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)



