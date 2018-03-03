---
title: Fonctions globales de Conversion HIMETRIC de pixel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlHiMetricToPixel
- atlwin/ATL::AtlPixelToHiMetric
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d670d667345c233fc499cda42194dfafa185dfe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pixelhimetric-conversion-global-functions"></a>Fonctions de Conversion de pixel/HIMETRIC Global
Ces fonctions prennent en charge la conversion vers et depuis le pixel et unités HIMETRIC.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Convertit des unités HIMETRIC (chaque unité représente 0,01 millimètre) en pixels.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Convertit des pixels en unités HIMETRIC (chaque unité représente 0,01 millimètre).|  
  
##  <a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
 Convertit la taille d'un objet en unités HIMETRIC (chaque unité représente 0,01 millimètre) vers une taille en pixels sur l'appareil à écran.  
  
 
```
extern void AtlHiMetricToPixel(
  const SIZEL* lpSizeInHiMetric, 
  LPSIZEL lpSizeInPix);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpSizeInHiMetric`  
 [in] Pointeur vers la taille de l’objet en unités HIMETRIC.  
  
 `lpSizeInPix`  
 [out] Pointeur vers où la taille de l’objet en pixels doit être retournée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM#49](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Configuration requise  
 **En-tête :** atlwin.h  
  
##  <a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
 Convertit la taille d'un objet en pixels sur l'appareil à écran vers une taille en unités HIMETRIC (chaque unité représente 0,01 millimètre).  
  
```
extern void AtlPixelToHiMetric(
    const SIZEL* lpSizeInPix, 
    LPSIZEL lpSizeInHiMetric);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpSizeInPix`  
 [in] Pointeur vers la taille de l’objet en pixels.  
  
 `lpSizeInHiMetric`  
 [out] Pointeur vers où la taille de l’objet en unités HIMETRIC doit être retournée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM#51](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Configuration requise  
 **En-tête :** atlwin.h  

## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)
