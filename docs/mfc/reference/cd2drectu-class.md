---
title: Classe de CD2DRectU | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- AFXRENDERTARGET/CD2DRectU
- AFXRENDERTARGET/CD2DRectU::CD2DRectU
- AFXRENDERTARGET/CD2DRectU::IsNull
dev_langs: C++
helpviewer_keywords:
- CD2DRectU [MFC], CD2DRectU
- CD2DRectU [MFC], IsNull
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2bf261f31f470862a506466a8815daef796743f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cd2drectu-class"></a>CD2DRectU, classe
Wrapper pour `D2D1_RECT_U`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](#cd2drectu)|Surchargé. Construit un `CD2DRectU` à partir de l’objet `D2D1_RECT_U` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRectU::IsNull](#isnull)|Retourne un `boolean` valeur qui indique si une expression ne contient aucune donnée valide ( `null`).|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](#operator_crect)|Convertit `CD2DRectU` à `CRect` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxrendertarget.h  
  
##  <a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
 Construit un objet CD2DRectU à partir de l’objet CRect.  
  
```  
CD2DRectU(const CRect& rect);  
CD2DRectU(const D2D1_RECT_U& rect);  
  CD2DRectU(const D2D1_RECT_U* rect);

 
CD2DRectU(
    UINT32 uLeft = 0,  
    UINT32 uTop = 0,  
    UINT32 uRight = 0,  
    UINT32 uBottom = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 rectangle source  
  
 `uLeft`  
 Coordonnée gauche source  
  
 `uTop`  
 coordonnée supérieure source  
  
 `uRight`  
 coordonnée droite source  
  
 `uBottom`  
 Coordonnée inférieure source  
  
##  <a name="isnull"></a>CD2DRectU::IsNull  
 Retourne une valeur booléenne qui indique si une expression ne contient aucune donnée valide (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si le du rectangle haut, gauche, bas et valeurs sont toujours égaux à 0 ; Sinon, FALSE.  
  
##  <a name="operator_crect"></a>CD2DRectU::operator CRect  
 Convertit CD2DRectU en objet CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle du rectangle de D2D.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)
