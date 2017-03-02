---
title: Classe de CD2DRectU | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DRectU
- afxrendertarget/CD2DRectU
dev_langs:
- C++
helpviewer_keywords:
- CD2DRectU class
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: 18
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
ms.openlocfilehash: 74c05d7f4be9b9308cdcb2b91a0455a4cd025dc1
ms.lasthandoff: 02/24/2017

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
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `D2D1_RECT_U`  
  
 `CD2DRectU`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="a-namecd2drectua--cd2drectucd2drectu"></a><a name="cd2drectu"></a>CD2DRectU::CD2DRectU  
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
  
##  <a name="a-nameisnulla--cd2drectuisnull"></a><a name="isnull"></a>CD2DRectU::IsNull  
 Retourne une valeur booléenne qui indique si une expression ne contient aucune donnée valide (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si ce rectangle en haut, gauche, inférieure et valeurs sont toujours égaux à 0 ; Sinon, FALSE.  
  
##  <a name="a-nameoperatorcrecta--cd2drectuoperator-crect"></a><a name="operator_crect"></a>CD2DRectU::operator CRect  
 Convertit CD2DRectU en objet CRect.  
  
```  
operator CRect();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle du rectangle de D2D.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

