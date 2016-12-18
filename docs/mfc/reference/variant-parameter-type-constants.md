---
title: "Constantes de type param&#232;tre variant | Microsoft Docs"
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
  - "VTS_YPOS_HIMETRIC"
  - "VTS_PICTURE"
  - "VTS_FONT"
  - "VTS_XPOS_HIMETRIC"
  - "VTS_XPOS_PIXELS"
  - "VTS_XSIZE_HIMETRIC"
  - "VTS_YPOS_PIXELS"
  - "VTS_TRISTATE"
  - "VTS_HANDLE"
  - "VTS_YSIZE_HIMETRIC"
  - "VTS_COLOR"
  - "VTS_OPTEXCLUSIVE"
  - "VTS_YSIZE_PIXELS"
  - "VTS_XSIZE_PIXELS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Variant (constantes de données)"
  - "Variants"
  - "Variants, constantes de type paramètre"
  - "VTS_COLOR (constante)"
  - "VTS_FONT (constante)"
  - "VTS_HANDLE (constante)"
  - "VTS_OPTEXCLUSIVE (constante)"
  - "VTS_PICTURE (constante)"
  - "VTS_TRISTATE (constante)"
  - "VTS_XPOS_HIMETRIC (constante)"
  - "VTS_XPOS_PIXELS (constante)"
  - "VTS_XSIZE_HIMETRIC (constante)"
  - "VTS_XSIZE_PIXELS (constante)"
  - "VTS_YPOS_HIMETRIC (constante)"
  - "VTS_YPOS_PIXELS (constante)"
  - "VTS_YSIZE_HIMETRIC (constante)"
  - "VTS_YSIZE_PIXELS (constante)"
ms.assetid: de99c7a9-7aae-4dc4-b723-40c6380543ab
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constantes de type param&#232;tre variant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les nouvelles constantes qui affichent les types variant de paramètres conçus pour une utilisation avec les classes de contrôle OLE de la bibliothèque MFC.  
  
 Voici une liste des constantes de la classe :  
  
##  <a name="_mfc_variant_data_constants"></a> Variantes des données constantes  
  
-   **VTS\_COLOR** Un entier de 32bit utilisé pour représenter une couleur RVB.  
  
-   **VTS\_FONT** Un pointeur à l'interface de **IFontDisp** d'une police de caractère OLE.  
  
-   **VTS\_HANDLE** Une valeur gérée par Windows.  
  
-   **VTS\_PICTURE** Un pointeur à l'interface de `IPictureDisp` d'un objet OLE image.  
  
-   **VTS\_OPTEXCLUSIVE** Un valeur de 16bit est utilisée pour un contrôle qui est destiné à être utilisé dans un groupe de contrôles, tels que les cases d'options.  Ce type exprime au conteneur que si un contrôle dans un groupe a une valeur de **VRAI**, tous les autres doivent être **FAUX**.  
  
-   **VTS\_TRISTATE** Un entier signé de 16bit utilisé pour les propriétés qui peut prendre l'une des trois valeurs possibles \(sélectionnées, vidées, indisponibles\), par exemple, une case à cocher.  
  
-   **VTS\_XPOS\_HIMETRIC** Un entier non signé de 32bit utilisé pour représenter une position sur l'axe des abscisses dans des unités **HIMETRIC**.  
  
-   **VTS\_YPOS\_HIMETRIC** Un entier non signé de 32bit utilisé pour représenter une position sur l'axe des ordonnées dans des unités **HIMETRIC**.  
  
-   **VTS\_XPOS\_PIXELS** Un entier non signé de 32bit utilisé pour représenter une position sur l'axe des abscisses en pixels.  
  
-   **VTS\_YPOS\_PIXELS** Un entier non signé de 32bit utilisé pour représenter une position sur l'axe des ordonnées en pixels.  
  
-   **VTS\_XSIZE\_PIXELS** Un entier non signé de 32bit utilisé pour représenter la largeur d'un objet d'écran en pixels.  
  
-   **VTS\_YSIZE\_PIXELS** Un entier non signé de 32bit utilisé pour représenter la hauteur d'un objet d'écran en pixels.  
  
-   **VTS\_XSIZE\_HIMETRIC** Un entier non signé de 32 bits utilisé pour représenter la largeur d'un objet d'écran en unités **HIMETRIC**.  
  
-   **VTS\_YSIZE\_HIMETRIC** Un entier non signé de 32 bits utilisé pour représenter la hauteur d'un objet d'écran en unités **HIMETRIC**.  
  
    > [!NOTE]
    >  Les constantes variantes supplémentaires ont été définies pour tous les types variants, à l'exception de **VTS\_FONT** et de **VTS\_PICTURE**, qui fournissent un pointeur à la constante de données variante.  Ces constantes sont nommées en utilisant la convention **VTS\_P**`constantname`.  Par exemple, **VTS\_PCOLOR** est un pointeur vers une constante de **VTS\_COLOR**.  
  
## Conditions requises  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)