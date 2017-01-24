---
title: "CSmartDockingInfo Class | Microsoft Docs"
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
  - "CSmartDockingInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmartDockingInfo class"
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSmartDockingInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit l'apparence des jetons intelligentes d'ancrage.  
  
## Syntaxe  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Constructeur par défaut.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSmartDockingInfo::CopyTo](../Topic/CSmartDockingInfo::CopyTo.md)|Copie les paramètres actuels intelligents d'informations de l'ancrage dans l'objet fourni de [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) .|  
  
### Membres de données  
  
|Nom|Description|  
|---------|-----------------|  
|[CSmartDockingInfo::m\_bUseThemeColorInShading](../Topic/CSmartDockingInfo::m_bUseThemeColorInShading.md)|Spécifie s'il faut utiliser le thème actuel couleurs lorsque l'infrastructure affiche le intelligentes d'ancrage.|  
|[CSmartDockingInfo::m\_clrBaseBackground](../Topic/CSmartDockingInfo::m_clrBaseBackground.md)|Spécifie la couleur d'arrière\-plan de base des jetons intelligentes d'ancrage.|  
|[CSmartDockingInfo::m\_clrToneDest](../Topic/CSmartDockingInfo::m_clrToneDest.md)|Spécifie la couleur qui remplace `m_clrToneSrc` dans les bitmaps intelligentes de point d'ancrage.|  
|[CSmartDockingInfo::m\_clrToneSrc](../Topic/CSmartDockingInfo::m_clrToneSrc.md)|Spécifie la couleur des bitmaps intelligentes de point d'ancrage.|  
|[CSmartDockingInfo::m\_clrTransparent](../Topic/CSmartDockingInfo::m_clrTransparent.md)|Spécifie la couleur des bitmaps intelligentes de point d'ancrage lorsqu'elles sont transparentes.|  
|[CSmartDockingInfo::m\_nCentralGroupOffset](../Topic/CSmartDockingInfo::m_nCentralGroupOffset.md)|Spécifie l'offset du groupe centre de jetons intelligentes d'ancrage de les limites du rectangle de groupe centre.|  
|[CSmartDockingInfo::m\_sizeTotal](../Topic/CSmartDockingInfo::m_sizeTotal.md)|Spécifie la taille totale de tous les jetons intelligentes d'ancrage dans un groupe.|  
|[CSmartDockingInfo::m\_uiMarkerBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerBmpResID.md)|Définit les identificateurs de ressource des bitmaps que l'infrastructure utilise pour le intelligentes d'ancrage qui ne sont pas mises en surbrillance.|  
|[CSmartDockingInfo::m\_uiMarkerLightBmpResID](../Topic/CSmartDockingInfo::m_uiMarkerLightBmpResID.md)|Définit les identificateurs de ressource des bitmaps que l'infrastructure utilise pour le intelligentes d'ancrage qui sont mises en surbrillance.|  
  
## Notes  
 L'infrastructure gère le intelligentes d'ancrage en interne.  L'illustration suivante montre le intelligentes standard d'ancrage :  
  
 ![Marqueurs d'ancrage actifs standard](../../mfc/reference/media/nextsdmarkers.png "nextSDmarkers")  
  
 Dans cette illustration, l'image sur la gauche montre un jeton intelligente du groupe centre d'ancrage qui n'a pas l'ancrage à un onglet activé.  L'image au milieu illustre un bord droit sur la marque intelligente d'ancrage.  L'image à droite affiche un jeton intelligente du groupe centre d'ancrage qui a l'ancrage à un onglet activé.  Le jeton intelligente du groupe centre d'ancrage a une bitmap principale et cinq bitmap intelligentes de point d'ancrage.  
  
 Vous pouvez personnaliser les paramètres suivants des jetons intelligentes d'ancrage :  
  
-   Couleur ;  Par exemple, vous pouvez remplacer la couleur bleue des jetons dans l'illustration par toute couleur définie par l'utilisateur.  
  
-   Couleur de transparence.  
  
-   Offset d'un jeton intelligente d'ancrage au groupe centre de la bordure du rectangle englobant.  
  
-   La bitmap principale qui représente le groupe central.  
  
-   Les bitmaps qui représente le arial regular et le intelligentes en surbrillance d'ancrage.  
  
 L'illustration suivante montre un exemple de balisage intelligentes d'ancrage qui ont été personnalisées :  
  
 ![Marqueurs d'ancrage actif personnalisés](../../mfc/reference/media/nextsdmarkerscustom.png "nextSDmarkersCustom")  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## Configuration requise  
 **en\-tête :** afxDockingManager.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)