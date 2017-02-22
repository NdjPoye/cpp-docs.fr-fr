---
title: "Routines d&#39;&#233;change de donn&#233;es de bo&#238;te de dialogue standard | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boîte de dialogue standard, routines d'échange de données"
ms.assetid: c6adb7f3-f9af-4cc5-a9ea-315c5b60ad1a
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Routines d&#39;&#233;change de donn&#233;es de bo&#238;te de dialogue standard
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique répertorie les routines de l'échange de données de boîtes de dialogue \(DDX\) standard utilisées pour les contrôles communs de la boîte de dialogue de MFC.  
  
> [!NOTE]
>  Les routines standard d'échange de données de boîtes de dialogue sont définies dans le fichier d'en\-tête afxdd\_.h.  Toutefois, les applications doivent inclure afxwin.h.  
  
### Fonctions DDX  
  
|||  
|-|-|  
|[DDX\_CBIndex](../Topic/DDX_CBIndex.md)|Initialise ou récupère l'index de la sélection actuelle d'un contrôle de zone de liste déroulante \(combo box\).|  
|[DDX\_CBString](../Topic/DDX_CBString.md)|Initialise ou récupère le contenu actuel du champ d'édition d'un contrôle zone de liste déroulante.|  
|[DDX\_CBStringExact](../Topic/DDX_CBStringExact.md)|Initialise ou récupère le contenu actuel du champ d'édition d'un contrôle zone de liste déroulante.|  
|[DDX\_Check](../Topic/DDX_Check.md)|Initialise ou récupère l'état actuel d'un contrôle de cases à cocher \(check box\).|  
|[DDX\_Control](../Topic/DDX_Control.md)|Sous\-classe un contrôle spécifié à l'intérieur d'une boîte de dialogue.|  
|[DDX\_DateTimeCtrl](../Topic/DDX_DateTimeCtrl.md)|Initialise ou récupère la date et\/ou les données de temps d'une date moment où d'un contrôle Time Picker.|  
|[DDX\_IPAddress](../Topic/DDX_IPAddress.md)|Initialise ou récupère la valeur actuelle d'un contrôle d'adresse IP.|  
|[DDX\_LBIndex](../Topic/DDX_LBIndex.md)|Initialise ou récupère l'index de la sélection actuelle d'un contrôle de zone de liste \(list box\).|  
|[DDX\_LBString](../Topic/DDX_LBString.md)|Initialise ou récupère la sélection actuelle dans un contrôle zone de liste.|  
|[DDX\_LBStringExact](../Topic/DDX_LBStringExact.md)|Initialise ou récupère la sélection actuelle dans un contrôle zone de liste.|  
|[DDX\_MonthCalCtrl](../Topic/DDX_MonthCalCtrl.md)|Initialise ou récupère la valeur actuelle d'un contrôle calendrier mensuel.|  
|[DDX\_Radio](../Topic/DDX_Radio.md)|Initialise ou récupère les index \(commençant à 0\) du contrôle du bouton radio qui est actuellement coché dans un groupe de contrôles de boutons radio.|  
|[DDX\_Scroll](../Topic/DDX_Scroll.md)|Initialise ou récupère la position actuelle du curseur de défilement d'un contrôle de défilement de type scroll.|  
|[DDX\_Slider](../Topic/DDX_Slider.md)|Initialise ou récupère la position actuelle du curseur de défilement d'un contrôle de défilement de type slider.|  
|[DDX\_Text](../Topic/DDX_Text.md)|Initialise ou récupère la valeur actuelle d'un contrôle d'édition.|  
  
## Voir aussi  
 [Routines de validation des données de boîte de dialogue standard](../../mfc/reference/standard-dialog-data-validation-routines.md)   
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)