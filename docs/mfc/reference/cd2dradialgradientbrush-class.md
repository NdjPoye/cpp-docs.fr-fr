---
title: Classe de CD2DRadialGradientBrush | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRadialGradientBrush
- afxrendertarget/CD2DRadialGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DRadialGradientBrush class
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
caps.latest.revision: 17
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
ms.openlocfilehash: 8b3fd7f468745567969ba1f7e9d6871a9060582b
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush, classe
Wrapper pour ID2D1RadialGradientBrush.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DRadialGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::CD2DRadialGradientBrush](#cd2dradialgradientbrush)|Construit un objet CD2DLinearGradientBrush.|  
|[CD2DRadialGradientBrush :: ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|Destructeur. Appelé lorsqu’un objet de pinceau de dégradé radial D2D est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::Attach](#attach)|Attache existant à l’objet interface de la ressource|  
|[CD2DRadialGradientBrush::Create](#create)|Crée un CD2DRadialGradientBrush. (Substitue [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DRadialGradientBrush::Destroy](#destroy)|Détruit un objet CD2DRadialGradientBrush. (Substitue [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DRadialGradientBrush::Detach](#detach)|Détache l’interface de la ressource à partir de l’objet|  
|[CD2DRadialGradientBrush::Get](#get)|Renvoie l’interface ID2D1RadialGradientBrush|  
|[CD2DRadialGradientBrush::GetCenter](#getcenter)|Extrait le centre de l’ellipse du dégradé|  
|[CD2DRadialGradientBrush::GetGradientOriginOffset](#getgradientoriginoffset)|Récupère le décalage de l’origine du dégradé par rapport au centre de l’ellipse du dégradé|  
|[CD2DRadialGradientBrush::GetRadiusX](#getradiusx)|Extrait le rayon x de l’ellipse du dégradé|  
|[CD2DRadialGradientBrush::GetRadiusY](#getradiusy)|Extrait le rayon y de l’ellipse du dégradé|  
|[CD2DRadialGradientBrush::SetCenter](#setcenter)|Spécifie le centre de l’ellipse de dégradé dans l’espace de coordonnées du pinceau|  
|[CD2DRadialGradientBrush::SetGradientOriginOffset](#setgradientoriginoffset)|Spécifie le décalage de l’origine du dégradé par rapport au centre de l’ellipse du dégradé|  
|[CD2DRadialGradientBrush::SetRadiusX](#setradiusx)|Spécifie le rayon x de l’ellipse de dégradé dans l’espace de coordonnées du pinceau|  
|[CD2DRadialGradientBrush::SetRadiusY](#setradiusy)|Spécifie le rayon y de l’ellipse de dégradé dans l’espace de coordonnées du pinceau|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|Renvoie l’interface ID2D1RadialGradientBrush|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRadialGradientBrush::m_pRadialGradientBrush](#m_pradialgradientbrush)|Pointeur vers un ID2D1RadialGradientBrush.|  
|[CD2DRadialGradientBrush::m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|Le centre, décalage d’origine du dégradé et x-radius rayon y de la forme de messagerie du dégradé.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DRadialGradientBrush`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dradialgradientbrusha--cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a>CD2DRadialGradientBrush :: ~ CD2DRadialGradientBrush  
 Destructeur. Appelé lorsqu’un objet de pinceau de dégradé radial D2D est détruit.  
  
```  
virtual ~CD2DRadialGradientBrush();
```  
  
##  <a name="a-nameattacha--cd2dradialgradientbrushattach"></a><a name="attach"></a>CD2DRadialGradientBrush::Attach  
 Attache existant à l’objet interface de la ressource  
  
```  
void Attach(ID2D1RadialGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Interface de la ressource existante. Ne peut pas être NULL  
  
##  <a name="a-namecd2dradialgradientbrusha--cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a>CD2DRadialGradientBrush::CD2DRadialGradientBrush  
 Construit un objet CD2DLinearGradientBrush.  
  
```  
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,  
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,  
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentTarget`  
 Pointeur vers la cible de rendu.  
  
 `gradientStops`  
 Pointeur vers un tableau de structures de D2D1_GRADIENT_STOP.  
  
 `gradientStopsCount`  
 Une valeur supérieure ou égale à 1 qui spécifie le nombre de points de dégradé dans le tableau gradientStops.  
  
 `RadialGradientBrushProperties`  
 Le centre, décalage d’origine du dégradé et x-radius rayon y de la forme de messagerie du dégradé.  
  
 `colorInterpolationGamma`  
 L’espace où la couleur interpolation entre les points de dégradé est effectuée.  
  
 `extendMode`  
 Le comportement du dégradé en dehors de la plage [0,1] normalisée.  
  
 `pBrushProperties`  
 Pointeur vers l’opacité et la transformation d’un pinceau.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dradialgradientbrushcreate"></a><a name="create"></a>CD2DRadialGradientBrush::Create  
 Crée un CD2DRadialGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="a-namedestroya--cd2dradialgradientbrushdestroy"></a><a name="destroy"></a>CD2DRadialGradientBrush::Destroy  
 Détruit un objet CD2DRadialGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dradialgradientbrushdetach"></a><a name="detach"></a>CD2DRadialGradientBrush::Detach  
 Détache l’interface de la ressource à partir de l’objet  
  
```  
ID2D1RadialGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface de la ressource détachée.  
  
##  <a name="a-namegeta--cd2dradialgradientbrushget"></a><a name="get"></a>CD2DRadialGradientBrush::Get  
 Renvoie l’interface ID2D1RadialGradientBrush  
  
```  
ID2D1RadialGradientBrush* Get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1RadialGradientBrush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-namegetcentera--cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a>CD2DRadialGradientBrush::GetCenter  
 Extrait le centre de l’ellipse du dégradé  
  
```  
CD2DPointF GetCenter() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Centre de l’ellipse du dégradé. Cette valeur est exprimée dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namegetgradientoriginoffseta--cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a>CD2DRadialGradientBrush::GetGradientOriginOffset  
 Récupère le décalage de l’origine du dégradé par rapport au centre de l’ellipse du dégradé  
  
```  
CD2DPointF GetGradientOriginOffset() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le décalage de l’origine du dégradé à partir du centre de l’ellipse du dégradé. Cette valeur est exprimée dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namegetradiusxa--cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a>CD2DRadialGradientBrush::GetRadiusX  
 Extrait le rayon x de l’ellipse du dégradé  
  
```  
FLOAT GetRadiusX() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rayon x de l’ellipse du dégradé. Cette valeur est exprimée dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namegetradiusya--cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a>CD2DRadialGradientBrush::GetRadiusY  
 Extrait le rayon y de l’ellipse du dégradé  
  
```  
FLOAT GetRadiusY() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le rayon y de l’ellipse du dégradé. Cette valeur est exprimée dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namempradialgradientbrusha--cd2dradialgradientbrushmpradialgradientbrush"></a><a name="m_pradialgradientbrush"></a>CD2DRadialGradientBrush::m_pRadialGradientBrush  
 Pointeur vers un ID2D1RadialGradientBrush.  
  
```  
ID2D1RadialGradientBrush* m_pRadialGradientBrush;  
```  
  
##  <a name="a-namemradialgradientbrushpropertiesa--cd2dradialgradientbrushmradialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a>CD2DRadialGradientBrush::m_RadialGradientBrushProperties  
 Le centre, décalage d’origine du dégradé et x-radius rayon y de la forme de messagerie du dégradé.  
  
```  
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;  
```  
  
##  <a name="a-nameoperatorid2d1radialgradientbrushstara--cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a>CD2DRadialGradientBrush::operator ID2D1RadialGradientBrush *  
 Renvoie l’interface ID2D1RadialGradientBrush  
  
```  
operator ID2D1RadialGradientBrush*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1RadialGradientBrush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-namesetcentera--cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a>CD2DRadialGradientBrush::SetCenter  
 Spécifie le centre de l’ellipse de dégradé dans l’espace de coordonnées du pinceau  
  
```  
void SetCenter(CD2DPointF point);
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Le centre de l’ellipse de dégradé dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namesetgradientoriginoffseta--cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a>CD2DRadialGradientBrush::SetGradientOriginOffset  
 Spécifie le décalage de l’origine du dégradé par rapport au centre de l’ellipse du dégradé  
  
```  
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```  
  
### <a name="parameters"></a>Paramètres  
 `gradientOriginOffset`  
 Le décalage de l’origine du dégradé à partir du centre de l’ellipse du dégradé  
  
##  <a name="a-namesetradiusxa--cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a>CD2DRadialGradientBrush::SetRadiusX  
 Spécifie le rayon x de l’ellipse de dégradé dans l’espace de coordonnées du pinceau  
  
```  
void SetRadiusX(FLOAT radiusX);
```  
  
### <a name="parameters"></a>Paramètres  
 `radiusX`  
 Le rayon x de l’ellipse du dégradé. Cette valeur se trouve dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namesetradiusya--cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a>CD2DRadialGradientBrush::SetRadiusY  
 Spécifie le rayon y de l’ellipse de dégradé dans l’espace de coordonnées du pinceau  
  
```  
void SetRadiusY(FLOAT radiusY);
```  
  
### <a name="parameters"></a>Paramètres  
 `radiusY`  
 Le rayon y de l’ellipse du dégradé. Cette valeur se trouve dans l’espace de coordonnées du pinceau  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

