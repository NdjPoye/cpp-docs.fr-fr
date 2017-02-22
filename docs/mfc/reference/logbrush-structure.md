---
title: "LOGBRUSH, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LOGBRUSH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOGBRUSH (structure)"
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LOGBRUSH, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `LOGBRUSH` définit le style, la couleur, et le modèle d'un pinceau physique.  Elle est utilisée par les fonctions Windows [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) et [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705).  
  
## Syntaxe  
  
```  
  
      typedef struct tag LOGBRUSH { /* lb */  
   UINT lbStyle;  
   COLORREF lbColor;  
   LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### Paramètres  
 `lbStyle`  
 Spécifie le style de pinceau.  Le membre `lbStyle` doit être l'un des styles suivants :  
  
-   Pinceau de modèle **BS\_DIBPATTERN**défini par une spécification \(DIB\) bitmap indépendante du périphérique.  Si `lbStyle` est **BS\_DIBPATTERN**, le membre de **lbHatch** contient un handle vers DIB compressé.  
  
-   **BS\_DIBPATTERNPT** pinceau de modèle défini par une spécification \(DIB\) bitmap indépendante du périphérique.  Si `lbStyle` est **BS\_DIBPATTERNPT**, le membre **lbHatch** contient un pointeur vers un DIB compressé.  
  
-   **BS\_HATCHED** pinceau hachuré.  
  
-   **BS\_HOLLOW** pinceau de cavité.  
  
-   **BS\_NULL** de même que **BS\_HOLLOW**.  
  
-   Pinceau de modèle **BS\_PATTERN**défini par un bitmap en mémoire.  
  
-   Pinceau plein **BS\_SOLID**.  
  
 `lbColor`  
 Spécifie la couleur dans laquelle le pinceau doit être dessiné.  Si `lbStyle` est le style **BS\_HOLLOW** ou **BS\_PATTERN**, **lbColor** est ignoré.  Si `lbStyle` est **BS\_DIBPATTERN** ou **BS\_DIBPATTERNBT**, le mot d'ordre inférieur de **lbColor** spécifie si les membres de **bmiColors** de la structure [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) contiennent des valeurs ou index RGB \(rouge vert bleu\) explicites dans la palette logique actuellement réalisée.  Le membre de **lbColor** doit être l'une des valeurs suivantes :  
  
-   **DIB\_PAL\_COLORS** la table des couleurs consiste en un tableau d'index 16 bits dans la palette logique actuellement réalisée.  
  
-   **DIB\_RGB\_COLORS** la table des couleurs contient les valeurs RVB littérales.  
  
 *lbHatch*  
 Spécifie un style de hachurage .  La signification dépend du style de pinceau défini par `lbStyle`.  Si `lbStyle` est **BS\_DIBPATTERN**, le membre **lbHatch** contient un handle vers un DIB compressé.  Si `lbStyle` est **BS\_DIBPATTERNPT**, le membre **lbHatch** contient un pointeur vers un DIB compressé.  Si `lbStyle` est **BS\_HATCHED**, le membre de **lbHatch** spécifie l'orientation des lignes utilisées pour créer la hachurage.  Cela peut avoir l'une des valeurs suivantes :  
  
-   `HS_BDIAGONAL` hachurage de gauche à droite, orienté à 45 degrés vers le haut.  
  
-   hachurage croisé horizontal et vertical `HS_CROSS`  
  
-   hachurage croisé de 45 degrés `HS_DIAGCROSS`  
  
-   `HS_FDIAGONAL` hachurage de gauche à droite, orienté à 45 degrés vers le bas.  
  
-   hachurage horizontal `HS_HORIZONTAL`  
  
-   de hachurage vertical `HS_VERTICAL`  
  
 Si `lbStyle` est **BS\_PATTERN**, **lbHatch** est un handle du bitmap qui définit le modèle.  Si `lbStyle` est **BS\_SOLID** ou **BS\_HOLLOW**, **lbHatch** est ignoré.  
  
## Notes  
 Bien que **lbColor** contrôle la couleur de premier plan d'un pinceau à hachures, les fonctions [CDC::SetBkMode](../Topic/CDC::SetBkMode.md) et [CDC::SetBkColor](../Topic/CDC::SetBkColor.md) contrôlent la couleur d'arrière\-plan.  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)