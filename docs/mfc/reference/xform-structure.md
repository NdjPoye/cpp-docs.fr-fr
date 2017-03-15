---
title: XForm, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2d23b3838f1e2dcabb2affb96fa6f18942581ff8
ms.lasthandoff: 02/24/2017

---
# <a name="xform-structure"></a>XFORM, structure
Le `XFORM` structure a la forme suivante :  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>Notes  
 Le `XFORM` structure spécifie un espace universel pour la transformation de l’espace de page. Le **eDx** et **eDy** membres spécifient les composants de la translation horizontale et verticale, respectivement. Le tableau suivant montre comment les autres membres sont utilisés, en fonction de l’opération :  
  
|Opération|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Cosinus de l’angle de rotation|Sinus de l’angle de rotation|Négatif sinus de l’angle de rotation|Cosinus de l’angle de rotation|  
|**Mise à l’échelle**|Composant de mise à l’échelle horizontale|Nothing|Nothing|Composant de mise à l’échelle verticale|  
|**Inclinaison**|Nothing|Constante de proportionnalité horizontal|Constante de proportionnalité verticale|Nothing|  
|**Réflexion**|Composant de réflexion horizontal|Nothing|Nothing|Composant de réflexion verticale|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)


