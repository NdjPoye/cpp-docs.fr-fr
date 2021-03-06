---
title: Classe de CD2DGradientBrush | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
dev_langs:
- C++
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3c01dbb3b14c13182afc85412b5c3ffa3ac0e9cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush, classe
La classe de base de la CD2DLinearGradientBrush et les classes CD2DRadialGradientBrush.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DGradientBrush::CD2DGradientBrush](#cd2dgradientbrush)|Construit un objet CD2DGradientBrush.|  
|[CD2DGradientBrush :: ~ CD2DGradientBrush](#cd2dgradientbrush__~cd2dgradientbrush)|Destructeur. Appelé lorsqu’un objet de pinceau de dégradé D2D est détruit.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DGradientBrush::Destroy](#destroy)|Détruit un objet CD2DGradientBrush. (Substitue [CD2DBrush::Destroy](../../mfc/reference/cd2dbrush-class.md#destroy).)|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGradientBrush::m_arGradientStops](#m_argradientstops)|Tableau des structures D2D1_GRADIENT_STOP.|  
|[CD2DGradientBrush::m_colorInterpolationGamma](#m_colorinterpolationgamma)|L’espace où la couleur une interpolation entre les points de dégradé est effectuée.|  
|[CD2DGradientBrush::m_extendMode](#m_extendmode)|Le comportement du dégradé en dehors de la plage normalisées [0,1].|  
|[CD2DGradientBrush::m_pGradientStops](#m_pgradientstops)|Pointeur vers un tableau de structures de D2D1_GRADIENT_STOP.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 `CD2DGradientBrush`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="_dtorcd2dgradientbrush"></a>  CD2DGradientBrush :: ~ CD2DGradientBrush  
 Destructeur. Appelé lorsqu’un objet de pinceau de dégradé D2D est détruit.  
  
```  
virtual ~CD2DGradientBrush();
```  
  
##  <a name="cd2dgradientbrush"></a>  CD2DGradientBrush::CD2DGradientBrush  
 Construit un objet CD2DGradientBrush.  
  
```  
CD2DGradientBrush(
    CRenderTarget* pParentTarget,  
    const D2D1_GRADIENT_STOP* gradientStops,  
    UINT gradientStopsCount,  
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
  
 `colorInterpolationGamma`  
 L’espace où la couleur une interpolation entre les points de dégradé est effectuée.  
  
 `extendMode`  
 Le comportement du dégradé en dehors de la plage normalisées [0,1].  
  
 `pBrushProperties`  
 Pointeur vers l’opacité et de transformation d’un pinceau.  
  
 `bAutoDestroy`  
 Indique que l’objet sera détruit par le propriétaire (pParentTarget).  
  
##  <a name="destroy"></a>  CD2DGradientBrush::Destroy  
 Détruit un objet CD2DGradientBrush.  
  
```  
virtual void Destroy();
```  
  
##  <a name="m_argradientstops"></a>  CD2DGradientBrush::m_arGradientStops  
 Tableau des structures D2D1_GRADIENT_STOP.  
  
```  
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;  
```  
  
##  <a name="m_colorinterpolationgamma"></a>  CD2DGradientBrush::m_colorInterpolationGamma  
 L’espace où la couleur une interpolation entre les points de dégradé est effectuée.  
  
```  
D2D1_GAMMA m_colorInterpolationGamma;  
```  
  
##  <a name="m_extendmode"></a>  CD2DGradientBrush::m_extendMode  
 Le comportement du dégradé en dehors de la plage normalisées [0,1].  
  
```  
D2D1_EXTEND_MODE m_extendMode;  
```  
  
##  <a name="m_pgradientstops"></a>  CD2DGradientBrush::m_pGradientStops  
 Pointeur vers un tableau de structures de D2D1_GRADIENT_STOP.  
  
```  
ID2D1GradientStopCollection* m_pGradientStops;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
