---
title: LOGPEN (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 12
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
ms.openlocfilehash: f3868d2ac6a7b18cfe43f7da8865aed0a3ecf88d
ms.lasthandoff: 02/24/2017

---
# <a name="logpen-structure"></a>LOGPEN, structure
Le `LOGPEN` structure définit le style, la largeur et la couleur d’un stylet, un objet de dessin utilisé pour dessiner les lignes et les bordures. Le [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) fonction utilise le `LOGPEN` structure.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *lopnStyle*  
 Spécifie le type de stylet. Ce membre peut être une des valeurs suivantes :  
  
- **PS_SOLID** crée un stylet continu.  
  
- **PS_DASH** crée un stylet en pointillés. (Valide uniquement lorsque la largeur du stylet est 1).  
  
- **PS_DOT** crée un stylet en pointillés. (Valide uniquement lorsque la largeur du stylet est 1).  
  
- **PS_DASHDOT** crée un stylet avec des points et des tirets alternés. (Valide uniquement lorsque la largeur du stylet est 1).  
  
- **PS_DASHDOTDOT** crée un stylet avec deux points et des tirets alternés. (Valide uniquement lorsque la largeur du stylet est 1).  
  
- **PS_NULL** crée un stylet null.  
  
- **PS_INSIDEFRAME** crée un stylet qui dessine une ligne dans le cadre des formes fermées produites par des fonctions de sortie GDI qui spécifient un rectangle englobant (par exemple, le **Ellipse**, **Rectangle**, `RoundRect`, `Pie`, et `Chord` les fonctions membres). Lorsque ce style est utilisé avec GDI des fonctions qui ne spécifient pas un rectangle englobant de sortie (par exemple, le `LineTo` fonction membre), la zone de dessin du stylet n’est pas limitée par un frame.  
  
     Si le stylet a la **PS_INSIDEFRAME** style et une couleur qui ne correspond pas à une couleur de la table logique, le stylet est dessiné avec une couleur dégradée. Le **PS_SOLID** style de stylet ne peut pas être utilisé pour créer un stylet avec une couleur dégradée. Le **PS_INSIDEFRAME** style est identique à **PS_SOLID** si la largeur du stylet est inférieur ou égal à 1.  
  
     Lors de la **PS_INSIDEFRAME** style est utilisé avec les objets GDI produites par des fonctions autres que **Ellipse**, **Rectangle**, et `RoundRect`, la ligne est peut-être pas complètement à l’intérieur du cadre spécifié.  
  
 *lopnWidth*  
 Spécifie la largeur du stylet, en unités logiques. Si le **lopnWidth** membre est 0, le stylet est de 1 pixel de large sur les périphériques raster quel que soit le mode de mappage en cours.  
  
 *lopnColor*  
 Spécifie la couleur du stylet.  
  
## <a name="remarks"></a>Remarques  
 Le **y** valeur dans le [POINT](../../mfc/reference/point-structure1.md) la structure de la **lopnWidth** membre n’est pas utilisé.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)


