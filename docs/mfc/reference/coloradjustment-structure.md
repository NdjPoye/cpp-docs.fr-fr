---
title: "COLORADJUSTMENT, structure | Microsoft Docs"
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
  - "COLORADJUSTMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLORADJUSTMENT (structure)"
ms.assetid: 67fc4e63-0e0e-4fcb-8c45-aa5ebfefa013
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLORADJUSTMENT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `COLORADJUSTMENT` définit les valeurs de réglage des couleurs utilisées par windows `StretchBlt` et **StretchDIBits** s'exécute lorsque le mode `StretchBlt` est **HALFTONE**.  
  
## Syntaxe  
  
```  
  
      typedef struct  tagCOLORADJUSTMENT {    /* ca */  
    WORD  caSize;  
    WORD  caFlags;  
    WORD  caIlluminantIndex;  
    WORD  caRedGamma;  
    WORD  caGreenGamma;  
    WORD  caBlueGamma;  
    WORD  caReferenceBlack;  
    WORD  caReferenceWhite;  
    SHORT caContrast;  
    SHORT caBrightness;  
    SHORT caColorfulness;  
    SHORT caRedGreenTint;  
} COLORADJUSTMENT;  
```  
  
#### Paramètres  
 *caSize*  
 Spécifie la taille, en octets, de la structure.  
  
 *caFlags*  
 Spécifie la façon dont l'image de sortie doit être préparée.  Ce membre peut être défini à **NULL** ou toute combinaison de valeurs suivantes :  
  
-   **CA\_NEGATIVE** spécifie que le négatif de l'image d'origine doit être affiché.  
  
-   **CA\_LOG\_FILTER** spécifie qu'une fonction logarithmique doit être appliquée à la densité finale des couleurs de sortie.  Cela augmente le contraste de couleur lorsque le luminosité est insuffisante.  
  
 *caIlluminantIndex*  
 Spécifie le luminosité de la source de lumière dans laquelle l'objet de l'image est affiché.  Ce membre peut être défini à l'une des valeurs suivantes :  
  
-   **ILLUMINANT\_EQUAL\_ENERGY**  
  
-   **ILLUMINANT\_A**  
  
-   **ILLUMINANT\_B**  
  
-   **ILLUMINANT\_C**  
  
-   **ILLUMINANT\_D50**  
  
-   **ILLUMINANT\_D55**  
  
-   **ILLUMINANT\_D65**  
  
-   **ILLUMINANT\_D75**  
  
-   **ILLUMINANT\_F2**  
  
-   **ILLUMINANT\_TURNGSTEN**  
  
-   **ILLUMINANT\_DAYLIGHT**  
  
-   **ILLUMINANT\_FLUORESCENT**  
  
-   **ILLUMINANT\_NTSC**  
  
 *caRedGamma*  
 Spécifie la n\-ième valeur de correction gamma de remplissage de rouge primaire des couleurs de source.  La valeur doit être comprise entre 2.500 et 65.000.  La valeur 10.000 signifie aucune correction gamma.  
  
 *caGreenGamma*  
 Spécifie la n\-ième valeur de correction gamma de remplissage de vert primaire des couleurs de source.  La valeur doit être comprise entre 2.500 et 65.000.  La valeur 10.000 signifie aucune correction gamma.  
  
 *caBlueGamma*  
 Spécifie la n\-ième valeur de correction gamma de remplissage de bleu primaire des couleurs de source.  La valeur doit être comprise entre 2.500 et 65.000.  La valeur 10.000 signifie aucune correction gamma.  
  
 *caReferenceBlack*  
 Spécifie la référence noire des couleurs de source.  Toutes les couleurs qui sont plus sombres que cela sont traitées comme noir.  La valeur doit être comprise entre 0 et 4.000.  
  
 *caReferenceWhite*  
 Spécifie la référence blanche des couleurs de source.  Toutes les couleurs qui sont plus légères que cela sont traitées comme des espaces.  La valeur doit être comprise entre 6.000 et 10.000.  
  
 *caContrast*  
 Spécifie la quantité de contrairement à appliquer à l'objet source.  La valeur doit être comprise entre \-100 et 100.  La valeur 0 signifie aucun ajustement de contraste.  
  
 *caBrightness*  
 Spécifie la quantité de contrairement à appliquer à l'objet source.  La valeur doit être comprise entre \-100 et 100.  La valeur 0 signifie aucun ajustement de luminosité.  
  
 *caColorfulness*  
 Spécifie la quantité de couleurs à appliquer à l'objet source.  La valeur doit être comprise entre \-100 et 100.  La valeur 0 signifie aucun ajustement de balance des couleurs.  
  
 *caRedGreenTint*  
 Spécifie la quantité de réglage de teinte de rouge ou de vert à appliquer à l'objet source.  La valeur doit être comprise entre \-100 et 100.  Les nombres positifs régleraient vers le rouge et les nombres négatifs vers ajuster le vert.  Un 0 signifie aucun ajustement de teinte.  
  
## Configuration requise  
 **Header:** wingdi.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)