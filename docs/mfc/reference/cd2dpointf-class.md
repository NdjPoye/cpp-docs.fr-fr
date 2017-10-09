---
title: Classe de CD2DPointF | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
dev_langs:
- C++
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 98435819aeb0e173074a4794939bee10b00b3233
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dpointf-class"></a>CD2DPointF, classe
Wrapper pour `D2D1_POINT_2F`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DPointF::CD2DPointF](#cd2dpointf)|Surchargé. Construit un `CD2DPointF` à partir de l’objet `D2D1_POINT_2F` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DPointF::operator CPoint](#operator_cpoint)|Convertit `CD2DPointF` à `CPoint` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `D2D1_POINT_2F`  
  
 `CD2DPointF`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="cd2dpointf"></a>CD2DPointF::CD2DPointF  
 Construit un objet CD2DPointF à partir de l’objet CPoint.  
  
```  
CD2DPointF(const CPoint& pt);    
CD2DPointF(const D2D1_POINT_2F& pt);    
CD2DPointF(const D2D1_POINT_2F* pt); 
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```  
  
### <a name="parameters"></a>Paramètres  
 `pt`  
 point de code source  
  
 `fX`  
 source X  
  
 `fY`  
 source Y  
  
##  <a name="operator_cpoint"></a>CD2DPointF::operator CPoint  
 Convertit CD2DPointF en objet CPoint.  
  
```  
operator CPoint();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle du point de D2D.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

