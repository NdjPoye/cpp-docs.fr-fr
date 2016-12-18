---
title: "CDrawingManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDrawingManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDrawingManager class"
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDrawingManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La classe d' `CDrawingManager` implémente les algorithmes complexes de dessin.  
  
## Syntaxe  
  
```  
class CDrawingManager : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDrawingManager::CDrawingManager](../Topic/CDrawingManager::CDrawingManager.md)|Construit un objet `CDrawingManager`.|  
|`CDrawingManager::~CDrawingManager`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDrawingManager::CreateBitmap\_32](../Topic/CDrawingManager::CreateBitmap_32.md)|Crée un .dib de 32 bits \(DIB\) que les applications peuvent écrire directement.|  
|[CDrawingManager::DrawAlpha](../Topic/CDrawingManager::DrawAlpha.md)|Affiche les bitmaps qui ont des pixels transparents ou translucides.|  
|[CDrawingManager::DrawRotated](../Topic/CDrawingManager::DrawRotated.md)|Fait pivoter un contrôle de contenu de contrôleur de domaine de source le rectangle donné par \+\/\- 90 degrés|  
|[CDrawingManager::DrawEllipse](../Topic/CDrawingManager::DrawEllipse.md)|Dessine une ellipse avec le remplissage et les couleurs de la bordure fournis.|  
|[CDrawingManager::DrawGradientRing](../Topic/CDrawingManager::DrawGradientRing.md)|Dessine une boucle et la remplit de dégradé de couleur.|  
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](../Topic/CDrawingManager::DrawLine,%20CDrawingManager::DrawLineA.md)|Dessine une ligne.|  
|[CDrawingManager::DrawRect](../Topic/CDrawingManager::DrawRect.md)|Dessine un rectangle avec le remplissage et les couleurs de la bordure fournis.|  
|[CDrawingManager::DrawShadow](../Topic/CDrawingManager::DrawShadow.md)|Dessine une ombre d'une zone rectangulaire.|  
|[CDrawingManager::Fill4ColorsGradient](../Topic/CDrawingManager::Fill4ColorsGradient.md)|Remplit une zone rectangulaire de deux de dégradé de couleur.|  
|[CDrawingManager::FillGradient](../Topic/CDrawingManager::FillGradient.md)|Remplit une zone rectangulaire de dégradé de couleur spécifié.|  
|[CDrawingManager::FillGradient2](../Topic/CDrawingManager::FillGradient2.md)|Remplit une zone rectangulaire de dégradé de couleur spécifié.  La direction de la modification des couleurs du dégradé est également spécifiée.|  
|[CDrawingManager::GrayRect](../Topic/CDrawingManager::GrayRect.md)|Remplit le rectangle de couleur grise spécifiée.|  
|[CDrawingManager::HighlightRect](../Topic/CDrawingManager::HighlightRect.md)|Met en surbrillance une zone rectangulaire.|  
|[CDrawingManager::HLStoRGB\_ONE](../Topic/CDrawingManager::HLStoRGB_ONE.md)|Convertit une couleur d'une représentation de HLS à une représentation RVB.|  
|[CDrawingManager::HLStoRGB\_TWO](../Topic/CDrawingManager::HLStoRGB_TWO.md)|Convertit une couleur d'une représentation de HLS à une représentation RVB.|  
|[CDrawingManager::HSVtoRGB](../Topic/CDrawingManager::HSVtoRGB.md)|Convertit une couleur d'une représentation de TSV à une représentation RVB.|  
|[CDrawingManager::HuetoRGB](../Topic/CDrawingManager::HuetoRGB.md)|Méthode d'assistance qui convertit une valeur de la teinte à un composant rouge, vert, bleu ou.|  
|[CDrawingManager::MirrorRect](../Topic/CDrawingManager::MirrorRect.md)|Retourne une zone rectangulaire.|  
|[CDrawingManager::PixelAlpha](../Topic/CDrawingManager::PixelAlpha.md)|Méthode d'assistance qui détermine la couleur finale d'un pixel translucide.|  
|[CDrawingManager::PrepareShadowMask](../Topic/CDrawingManager::PrepareShadowMask.md)|Crée une bitmap qui peut servir d'ombre.|  
|[CDrawingManager::RGBtoHSL](../Topic/CDrawingManager::RGBtoHSL.md)|Convertit une couleur d'une représentation RVB à une représentation NSL.|  
|[CDrawingManager::RGBtoHSV](../Topic/CDrawingManager::RGBtoHSV.md)|Convertit une couleur d'une représentation RVB à une représentation de TSV.|  
|[CDrawingManager::SetAlphaPixel](../Topic/CDrawingManager::SetAlphaPixel.md)|Méthode d'assistance qui couleurs un pixel partiellement transparent dans une bitmap.|  
|[CDrawingManager::SetPixel](../Topic/CDrawingManager::SetPixel.md)|Méthode d'assistance qui modifie un pixel unique dans une bitmap en couleur spécifiée.|  
|[CDrawingManager::SmartMixColors](../Topic/CDrawingManager::SmartMixColors.md)|Regroupe deux couleurs selon un taux pondérées.|  
  
## Notes  
 La classe d' `CDrawingManager` fournit des fonctions pour les ombres de dessin, les dégradés de couleur, et les rectangles mis en surbrillance.  Elle exécute également une fusion alpha.  Vous pouvez utiliser cette classe pour modifier directement l'interface utilisateur de votre application.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md)  
  
## Configuration requise  
 **en\-tête :** afxdrawmanager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)