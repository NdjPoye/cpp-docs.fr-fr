---
title: Classe de CD2DSizeU | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::CD2DSizeU
- AFXRENDERTARGET/CD2DSizeU::IsNull
dev_langs:
- C++
helpviewer_keywords:
- CD2DSizeU class
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
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
ms.openlocfilehash: a43ea5448a0b0d09d4cf27eafb01a4d4b610e4f5
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dsizeu-class"></a>CD2DSizeU, classe
Wrapper pour D2D1_SIZE_U.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](#cd2dsizeu)|Surchargé. Construit un `CD2DSizeU` à partir de l’objet `D2D1_SIZE_U` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DSizeU::IsNull](#isnull)|Retourne un `boolean` valeur qui indique si une expression ne contient aucune donnée valide ( `null`).|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](#operator_csize)|Convertit `CD2DSizeU` à `CSize` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="cd2dsizeu"></a>CD2DSizeU::CD2DSizeU  
 Construit un objet CD2DSizeU à partir de l’objet CSize.  
  
```  
CD2DSizeU(const CSize& size);  
CD2DSizeU(const D2D1_SIZE_U& size);  
  CD2DSizeU(const D2D1_SIZE_U* size);

 
CD2DSizeU(
    UINT32 cx = 0,  
    UINT32 cy = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 taille de la source  
  
 `cx`  
 largeur de la source  
  
 `cy`  
 hauteur de la source  
  
##  <a name="isnull"></a>CD2DSizeU::IsNull  
 Retourne une valeur booléenne qui indique si une expression ne contient aucune donnée valide (Null).  
  
```  
BOOL IsNull() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 TRUE si la largeur et la hauteur sont vides ; Sinon, FALSE.  
  
##  <a name="operator_csize"></a>CD2DSizeU::operator CSize  
 Convertit CD2DSizeU en objet CSize.  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>Valeur de retour  
 Valeur actuelle de la taille de D2D.  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

