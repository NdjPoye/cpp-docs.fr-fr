---
title: Structure BITMAP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- BITMAP
dev_langs:
- C++
helpviewer_keywords:
- BITMAP structure
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: cd7e63cfe9e7a0f2305ca5c3cd7c2571a080a718
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="bitmap-structure"></a>Structure BITMAP
Le **BITMAP** structure définit la hauteur, largeur, format de couleur et les valeurs de bits de la bitmap logique**.**  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct tagBITMAP {  /* bm */  
    int bmType;  
    int bmWidth;  
    int bmHeight;  
    int bmWidthBytes;  
    BYTE bmPlanes;  
    BYTE bmBitsPixel;  
    LPVOID bmBits;  
} BITMAP;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *bmType*  
 Spécifie le type d’image bitmap. Pour les bitmaps logiques, ce membre doit être 0.  
  
 *bmWidth*  
 Spécifie la largeur de l’image bitmap en pixels. La largeur doit être supérieure à 0.  
  
 *bmHeight*  
 Spécifie la hauteur de la bitmap dans les lignes de la trame. La hauteur doit être supérieure à 0.  
  
 *bmWidthBytes*  
 Spécifie le nombre d’octets dans chaque ligne de la trame. Cette valeur doit être un nombre pair, car l’interface graphique (GDI) suppose que les valeurs de bits de la bitmap forment un tableau d’entiers de (2 octets). En d’autres termes, **bmWidthBytes** \* 8 doit être au prochain multiple de 16 supérieure ou égale à la valeur obtenue lorsque le **bmWidth** membre est multiplié par la **bmBitsPixel** membre.  
  
 *bmPlanes*  
 Spécifie le nombre de plans de couleur de l’image bitmap.  
  
 *bmBitsPixel*  
 Spécifie le nombre de bits de couleur adjacent sur chaque plan nécessaire à la définition d’un pixel.  
  
 *bmBits*  
 Pointe vers l’emplacement des valeurs de bits de l’image bitmap. Le **bmBits** membre doit être un pointeur long vers un tableau de valeurs de 1 octet.  
  
## <a name="remarks"></a>Remarques  
 Les formats bitmap actuellement utilisés sont monochrome et couleur. La bitmap monochrome utilise un format 1 bit 1-plan. Chaque analyse est un multiple de 16 bits.  
  
 Les analyses sont organisées comme suit pour un bitmap monochrome de hauteur *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Les pixels sur un périphérique monochrome sont noir ou blanc. Si le bit correspondant dans la bitmap est 1, le pixel est activé (blanc). Si le bit correspondant dans la bitmap est 0, le pixel est désactivé (noir).  
  
 Tous les périphériques prennent en charge les bitmaps qui ont le **RC_BITBLT** bit défini dans le **RASTERCAPS** index de la [CDC::GetDeviceCaps](../../mfc/reference/cdc-class.md#getdevicecaps) fonction membre.  
  
 Chaque périphérique possède son propre format de couleur unique. Pour transférer une image bitmap à partir d’un périphérique à un autre, utilisez la [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) et [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973) fonctions de Windows.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** wingdi.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect)

