---
title: XForm, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XFORM
dev_langs: C++
helpviewer_keywords: XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3f6f7121b5cc93c3f8f6f34f22d16cef888bbf15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
 Le `XFORM` structure spécifie un espace universel pour la transformation de l’espace de page. Le **eDx** et **eDy** membres spécifient les composants de traduction horizontales et verticales, respectivement. Le tableau suivant montre comment les autres membres sont utilisés, selon l’opération :  
  
|Opération|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Cosinus de l’angle de rotation|Sinus de l’angle de rotation|Négatif sinus de l’angle de rotation|Cosinus de l’angle de rotation|  
|**Mise à l’échelle**|Composant de mise à l’échelle horizontale|Nothing|Nothing|Composant de mise à l’échelle verticale|  
|**Inclinaison**|Nothing|Constante de proportionnalité horizontal|Constante de proportionnalité vertical|Nothing|  
|**Réflexion**|Composant de réflexion horizontal|Nothing|Nothing|Composant de réflexion vertical|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

