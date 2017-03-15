---
title: Classe de CD2DLinearGradientBrush | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- afxrendertarget/CD2DLinearGradientBrush
- CD2DLinearGradientBrush
dev_langs:
- C++
helpviewer_keywords:
- CD2DLinearGradientBrush class
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
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
ms.openlocfilehash: dd288478a751d921cc4d9fcd9433e391275cee66
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush, classe
Wrapper pour ID2D1LinearGradientBrush.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](#cd2dlineargradientbrush)|Construit un objet CD2DLinearGradientBrush.|  
|[CD2DLinearGradientBrush :: ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|Destructeur. Appelé lorsqu’un objet de pinceau de dégradé linéaire D2D est détruit.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::Attach](#attach)|Attache existant à l’objet interface de la ressource|  
|[CD2DLinearGradientBrush::Create](#create)|Crée un CD2DLinearGradientBrush. (Substitue [CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create).)|  
|[CD2DLinearGradientBrush::Destroy](#destroy)|Détruit un objet CD2DLinearGradientBrush. (Substitue [CD2DGradientBrush::Destroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy).)|  
|[CD2DLinearGradientBrush::Detach](#detach)|Détache l’interface de la ressource à partir de l’objet|  
|[CD2DLinearGradientBrush::Get](#get)|Renvoie l’interface ID2D1LinearGradientBrush|  
|[CD2DLinearGradientBrush::GetEndPoint](#getendpoint)|Récupère les coordonnées de fin du dégradé linéaire|  
|[CD2DLinearGradientBrush::GetStartPoint](#getstartpoint)|Récupère les coordonnées de début du dégradé linéaire|  
|[CD2DLinearGradientBrush::SetEndPoint](#setendpoint)|Définit les coordonnées de fin du dégradé linéaire dans l’espace de coordonnées du pinceau|  
|[CD2DLinearGradientBrush::SetStartPoint](#setstartpoint)|Définit les coordonnées de début du dégradé linéaire dans l’espace de coordonnées du pinceau|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|Renvoie l’interface ID2D1LinearGradientBrush|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DLinearGradientBrush::m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|Les points de début et fin du dégradé.|  
|[CD2DLinearGradientBrush::m_pLinearGradientBrush](#m_plineargradientbrush)|Pointeur vers un ID2D1LinearGradientBrush.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 `CD2DLinearGradientBrush`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-namedtorcd2dlineargradientbrusha--cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a>CD2DLinearGradientBrush :: ~ CD2DLinearGradientBrush  
 Destructeur. Appelé lorsqu’un objet de pinceau de dégradé linéaire D2D est détruit.  
  
```  
virtual ~CD2DLinearGradientBrush();
```  
  
##  <a name="a-nameattacha--cd2dlineargradientbrushattach"></a><a name="attach"></a>CD2DLinearGradientBrush::Attach  
 Attache existant à l’objet interface de la ressource  
  
```  
void Attach(ID2D1LinearGradientBrush* pResource);
```  
  
### <a name="parameters"></a>Paramètres  
 `pResource`  
 Interface de la ressource existante. Ne peut pas être NULL  
  
##  <a name="a-namecd2dlineargradientbrusha--cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a>CD2DLinearGradientBrush::CD2DLinearGradientBrush  
 Construit un objet CD2DLinearGradientBrush.  
  
```  
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,  
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
  
 `LinearGradientBrushProperties`  
 Les points de début et fin du dégradé.  
  
 `colorInterpolationGamma`  
 L’espace où la couleur interpolation entre les points de dégradé est effectuée.  
  
 `extendMode`  
 Le comportement du dégradé en dehors de la plage [0,1] normalisée.  
  
 `pBrushProperties`  
 Pointeur vers l’opacité et la transformation d’un pinceau.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="a-namecreatea--cd2dlineargradientbrushcreate"></a><a name="create"></a>CD2DLinearGradientBrush::Create  
 Crée un CD2DLinearGradientBrush.  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `pRenderTarget`  
 Pointeur vers la cible de rendu.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne S_OK. Sinon, elle retourne un code d’erreur HRESULT.  
  
##  <a name="a-namedestroya--cd2dlineargradientbrushdestroy"></a><a name="destroy"></a>CD2DLinearGradientBrush::Destroy  
 Détruit un objet CD2DLinearGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="a-namedetacha--cd2dlineargradientbrushdetach"></a><a name="detach"></a>CD2DLinearGradientBrush::Detach  
 Détache l’interface de la ressource à partir de l’objet  
  
```  
ID2D1LinearGradientBrush* Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers l’interface de la ressource détachée.  
  
##  <a name="a-namegeta--cd2dlineargradientbrushget"></a><a name="get"></a>CD2DLinearGradientBrush::Get  
 Renvoie l’interface ID2D1LinearGradientBrush  
  
```  
ID2D1LinearGradientBrush* Get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1LinearGradientBrush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-namegetendpointa--cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a>CD2DLinearGradientBrush::GetEndPoint  
 Récupère les coordonnées de fin du dégradé linéaire  
  
```  
CD2DPointF GetEndPoint() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les coordonnées finales à deux dimensions du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namegetstartpointa--cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a>CD2DLinearGradientBrush::GetStartPoint  
 Récupère les coordonnées de début du dégradé linéaire  
  
```  
CD2DPointF GetStartPoint() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Les coordonnées à deux dimensions de début du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namemlineargradientbrushpropertiesa--cd2dlineargradientbrushmlineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a>CD2DLinearGradientBrush::m_LinearGradientBrushProperties  
 Les points de début et fin du dégradé.  
  
```  
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;  
```  
  
##  <a name="a-namemplineargradientbrusha--cd2dlineargradientbrushmplineargradientbrush"></a><a name="m_plineargradientbrush"></a>CD2DLinearGradientBrush::m_pLinearGradientBrush  
 Pointeur vers un ID2D1LinearGradientBrush.  
  
```  
ID2D1LinearGradientBrush* m_pLinearGradientBrush;  
```  
  
##  <a name="a-nameoperatorid2d1lineargradientbrushstara--cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a>CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush *  
 Renvoie l’interface ID2D1LinearGradientBrush  
  
```  
operator ID2D1LinearGradientBrush*();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une interface de ID2D1LinearGradientBrush ou NULL si l’objet n’est pas encore initialisé.  
  
##  <a name="a-namesetendpointa--cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a>CD2DLinearGradientBrush::SetEndPoint  
 Définit les coordonnées de fin du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
```  
void SetEndPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Les coordonnées finales à deux dimensions du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
##  <a name="a-namesetstartpointa--cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a>CD2DLinearGradientBrush::SetStartPoint  
 Définit les coordonnées de début du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
```  
void SetStartPoint(CD2DPointF point);
```  
  
### <a name="parameters"></a>Paramètres  
 `point`  
 Les coordonnées à deux dimensions de début du dégradé linéaire dans l’espace de coordonnées du pinceau  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

