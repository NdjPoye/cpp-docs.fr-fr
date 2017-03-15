---
title: LOGBRUSH (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
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
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>LOGBRUSH, structure
Le `LOGBRUSH` structure définit le style, la couleur et le motif d’un pinceau physique. Il est utilisé par Windows [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) et [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) fonctions.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lbStyle`  
 Spécifie le style de pinceau. Le `lbStyle` membre doit être un des styles suivants :  
  
- **BS_DIBPATTERN** un pinceau de modèle défini par une spécification de bitmap indépendante du périphérique (DIB). Si `lbStyle` est **BS_DIBPATTERN**, le **lbHatch** membre contient un handle vers un DIB compressé.  
  
- **BS_DIBPATTERNPT** un pinceau de modèle défini par une spécification de bitmap indépendante du périphérique (DIB). Si `lbStyle` est **BS_DIBPATTERNPT**, le **lbHatch** membre contient un pointeur vers un DIB compressé.  
  
- **BS_HATCHED** hachée pinceau.  
  
- **BS_HOLLOW** creuse pinceau.  
  
- **BS_NULL** identique **BS_HOLLOW**.  
  
- **BS_PATTERN** modèle pinceau défini par un bitmap de la mémoire.  
  
- **BS_SOLID** pinceau solide.  
  
 `lbColor`  
 Spécifie la couleur dans laquelle le pinceau doit être dessiné. Si `lbStyle` est la **BS_HOLLOW** ou **BS_PATTERN** style, **lbColor** est ignoré. Si `lbStyle` est **BS_DIBPATTERN** ou **BS_DIBPATTERNBT**, le mot de poids faible de **lbColor** Spécifie si les **bmiColors** membres de la [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) structure contiennent explicite rouge, vert, bleu (valeurs) ou index dans la palette logique actuellement réalisée. Le **lbColor** membre doit être une des valeurs suivantes :  
  
- **DIB_PAL_COLORS** la table des couleurs se compose d’un tableau d’index 16 bits dans la palette logique actuellement réalisée.  
  
- **DIB_RGB_COLORS** la table des couleurs contient des valeurs littérales.  
  
 *lbHatch*  
 Spécifie le style de hachurage. La signification varie selon le style de pinceau défini par `lbStyle`. Si `lbStyle` est **BS_DIBPATTERN**, le **lbHatch** membre contient un handle vers un DIB compressé. Si `lbStyle` est **BS_DIBPATTERNPT**, le **lbHatch** membre contient un pointeur vers un DIB compressé. Si `lbStyle` est **BS_HATCHED**, le **lbHatch** membre spécifie l’orientation des lignes utilisées pour créer le hachurage. Il peut prendre l’une des valeurs suivantes :  
  
- `HS_BDIAGONAL`Un hachurage de 45 degrés vers le haut, de gauche à droite  
  
- `HS_CROSS`Hachurage horizontal et vertical  
  
- `HS_DIAGCROSS`hachurage de 45 degrés  
  
- `HS_FDIAGONAL`Un hachurage de 45 degrés vers le bas, de gauche à droite  
  
- `HS_HORIZONTAL`Hachage horizontal  
  
- `HS_VERTICAL`Hachage vertical  
  
 Si `lbStyle` est **BS_PATTERN**, **lbHatch** est un handle de bitmap qui définit le modèle. Si `lbStyle` est **BS_SOLID** ou **BS_HOLLOW**, **lbHatch** est ignoré.  
  
## <a name="remarks"></a>Remarques  
 Bien que **lbColor** contrôle la couleur de premier plan d’un pinceau à hachure, la [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) et [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) fonctions de contrôlent la couleur d’arrière-plan.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


