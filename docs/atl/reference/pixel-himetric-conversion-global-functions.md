---
title: Fonctions globales de Conversion HIMETRIC de pixel | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: ecb1b1b2-7e9d-4fbc-a855-16252d2d794c
caps.latest.revision: 19
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
ms.openlocfilehash: efb7e7da896aea4e377225f4c1e2c9948e635705
ms.lasthandoff: 02/24/2017

---
# <a name="pixelhimetric-conversion-global-functions"></a>Fonctions de Conversion de pixel/HIMETRIC Global
Ces fonctions prennent en charge la conversion vers et depuis des pixels et unités HIMETRIC.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlHiMetricToPixel](#atlhimetrictopixel)|Convertit des unités HIMETRIC (chaque unité représente 0,01 millimètre) en pixels.|  
|[AtlPixelToHiMetric](#atlpixeltohimetric)|Convertit des pixels en unités HIMETRIC (chaque unité représente 0,01 millimètre).|  
  
##  <a name="a-nameatlhimetrictopixela--atlhimetrictopixel"></a><a name="atlhimetrictopixel"></a>AtlHiMetricToPixel  
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
 [!code-cpp[NVC_ATL_COM&49;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_1.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-nameatlpixeltohimetrica--atlpixeltohimetric"></a><a name="atlpixeltohimetric"></a>AtlPixelToHiMetric  
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
 [!code-cpp[NVC_ATL_COM&#51;](../../atl/codesnippet/cpp/pixel-himetric-conversion-global-functions_2.cpp)]  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  

## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

