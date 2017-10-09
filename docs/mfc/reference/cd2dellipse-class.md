---
title: Classe de CD2DEllipse | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
dev_langs:
- C++
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 97a14391eda7716b71560a5f1e65a4bd65a329d1
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dellipse-class"></a>CD2DEllipse, classe
Wrapper pour `D2D1_ELLIPSE`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DEllipse : public D2D1_ELLIPSE;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DEllipse::CD2DEllipse](#cd2dellipse)|Surchargé. Construit un `CD2DEllipse` à partir de l’objet `D2D1_ELLIPSE` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `D2D1_ELLIPSE`  
  
 `CD2DEllipse`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="cd2dellipse"></a>CD2DEllipse::CD2DEllipse  
 Construit un objet CD2DEllipse à partir de l’objet de CD2DRectF.  
  
```  
CD2DEllipse(const CD2DRectF& rect);  
CD2DEllipse(const D2D1_ELLIPSE& ellipse);  
  CD2DEllipse(const D2D1_ELLIPSE* ellipse);

 
CD2DEllipse(
    const CD2DPointF& ptCenter,  
    const CD2DSizeF& sizeRadius);
```  
  
### <a name="parameters"></a>Paramètres  
 `rect`  
 rectangle source  
  
 `ellipse`  
 sélection de la source  
  
 `ptCenter`  
 Le point central de l’ellipse.  
  
 `sizeRadius`  
 Le rayon X et le rayon Y de l’ellipse.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

