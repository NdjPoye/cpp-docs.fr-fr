---
title: CD2DBrushProperties classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CD2DBrushProperties
- AFXRENDERTARGET/CD2DBrushProperties::CommonInit
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrushProperties [MFC], CD2DBrushProperties
- CD2DBrushProperties [MFC], CommonInit
ms.assetid: c77d717f-0a16-4d74-b2ce-0ae1766ed6f9
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: ce10f805968b31f0d3a832891c1e0e378277b626
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dbrushproperties-class"></a>CD2DBrushProperties, classe
Wrapper pour `D2D1_BRUSH_PROPERTIES`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CD2DBrushProperties : public D2D1_BRUSH_PROPERTIES;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrushProperties::CD2DBrushProperties](#cd2dbrushproperties)|Surchargé. Crée un `CD2D_BRUSH_PROPERTIES` structure|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CD2DBrushProperties::CommonInit](#commoninit)|Initialise l’objet|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `D2D1_BRUSH_PROPERTIES`  
  
 `CD2DBrushProperties`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrendertarget.h  
  
##  <a name="cd2dbrushproperties"></a>CD2DBrushProperties::CD2DBrushProperties  
 Crée une structure CD2D_BRUSH_PROPERTIES  
  
```  
CD2DBrushProperties();  
CD2DBrushProperties(FLOAT _opacity);

 
CD2DBrushProperties(
    D2D1_MATRIX_3X2_F _transform,  
    FLOAT _opacity = 1.);
```  
  
### <a name="parameters"></a>Paramètres  
 `_opacity`  
 Opacité de base du pinceau. La valeur par défaut est 1,0.  
  
 `_transform`  
 La transformation à appliquer au pinceau  
  
##  <a name="commoninit"></a>CD2DBrushProperties::CommonInit  
 Initialise l’objet  
  
```  
void CommonInit();
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

