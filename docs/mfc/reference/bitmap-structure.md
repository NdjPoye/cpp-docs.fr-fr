---
title: "Structure BITMAP | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BITMAP (structure)"
ms.assetid: 05d33b4d-7232-4643-a108-87dda8ff5f22
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Structure BITMAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure **BITMAP** définit la hauteur, la largeur, le format de couleur, et les valeurs de bits d'une image bitmap**.**  
  
## Syntaxe  
  
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
  
#### Paramètres  
 *bmType*  
 Spécifie le type d'image bitmap.  Pour les bitmaps logiques, ce membre doit être égal à 0.  
  
 *bmWidth*  
 Spécifie la largeur de l'image bitmap en pixels.  La largeur doit être supérieure à 0.  
  
 *bmHeight*  
 Spécifie la hauteur de la bitmap dans les lignes en trames.  La hauteur doit être supérieure à 0.  
  
 *bmWidthBytes*  
 Spécifie le nombre d'octets dans chaque ligne en frames.  Cette valeur doit être un nombre pair puisque le Graphics Device Interface \(GDI\) suppose que les valeurs de bits d'un formulaire bitmap correspond à un tableau d'entiers \(2 octets\).  En d'autres termes, **bmWidthBytes** \* 8 doit être le multiple de 16 suivant supérieur ou égal à la valeur obtenue lorsque **bmWidth** est multipliée par le membre **bmBitsPixel**.  
  
 *bmPlanes*  
 Spécifie le nombre de planes de couleur dans la bitmap.  
  
 *bmBitsPixel*  
 Spécifie le nombre de bits de couleur adjacents sur chaque plan nécessaire pour définir un pixel.  
  
 *bmBits*  
 Pointe vers l'emplacement des valeurs de bits de la bitmap.  Le membre **bmBits** doit être un pointeur long vers un tableau de valeurs de 1 octets.  
  
## Notes  
 Les formats bitmap actuellement utilisés sont monochromes et couleur.  La bitmap monochrome utilise un 1 bits, 1 format plat.  Chaque analyse est un multiple de 16 bits.  
  
 Les analyses sont classés comme suit pour une bitmap monochrome de hauteur *n*:  
  
 `Scan 0`  
  
 `Scan 1`  
  
 `.`  
  
 `.`  
  
 `.`  
  
 `Scan n-2`  
  
 `Scan n-1`  
  
 Les pixels sur un périphérique monochrome sont noir et blanc.  Si le bit correspondant dans la bitmap est 1, le pixel est activée \(blanc\).  Si le bit correspondant dans la bitmap est 0, le pixel est désactivé \(noir\).  
  
 Tous les appareils prennent en charge les bitmaps qui ont **RC\_BITBLT** bit défini dans l'index **RASTERCAPS** de la fonction membre [CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md).  
  
 Chaque périphérique possède son propre format de couleur unique.  Afin de transférer une bitmap d'un appareil vers une autre, utilisez les fonctions Windows de [GetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd144879) et de [SetDIBits](http://msdn.microsoft.com/library/windows/desktop/dd162973).  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CBitmap::CreateBitmapIndirect](../Topic/CBitmap::CreateBitmapIndirect.md)