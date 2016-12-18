---
title: "CPalette Class | Microsoft Docs"
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
  - "CPalette"
  - "HPALETTE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "palettes de couleurs, MFC"
  - "CPalette class"
  - "HPALETTE"
ms.assetid: 8cd95498-53ed-4852-85e1-70e522541114
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPalette Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule une palette de couleurs windows.  
  
## Syntaxe  
  
```  
class CPalette : public CGdiObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPalette::CPalette](../Topic/CPalette::CPalette.md)|Construit un objet d' `CPalette` sans la palette attachée windows.  Vous devez initialiser l'objet d' `CPalette` avec une des fonctions membres d'initialisation avant qu'elle puisse être utilisée.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md)|Remplace les entrées dans la palette logique identifiée par l'objet d' `CPalette` .  L'application ne doit pas conserver sa zone cliente, car windows mappe les nouvelles entrées dans la palette système immédiatement.|  
|[CPalette::CreateHalftonePalette](../Topic/CPalette::CreateHalftonePalette.md)|Crée une palette de demi\-teintes pour le contexte de périphérique et la attaché à l'objet d' `CPalette` .|  
|[CPalette::CreatePalette](../Topic/CPalette::CreatePalette.md)|Crée une palette de couleurs windows et l'attache à l'objet d' `CPalette` .|  
|[CPalette::FromHandle](../Topic/CPalette::FromHandle.md)|Retourne un pointeur vers un objet d' `CPalette` une fois donné un handle vers un objet de la palette de windows.|  
|[CPalette::GetEntryCount](../Topic/CPalette::GetEntryCount.md)|Récupère le nombre d'entrées de la palette dans une palette logique.|  
|[CPalette::GetNearestPaletteIndex](../Topic/CPalette::GetNearestPaletteIndex.md)|Retourne l'index de l'entrée dans la palette logique qui correspond le mieux à une valeur de couleur.|  
|[CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)|Extrait une plage des entrées de la palette dans une palette logique.|  
|[CPalette::ResizePalette](../Topic/CPalette::ResizePalette.md)|Modifie la taille de la palette logique spécifiée par l'objet d' `CPalette` au nombre spécifié d'entrée.|  
|[CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)|Définit les valeurs de couleur et de balises RVB dans une plage des entrées dans une palette logique.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CPalette::operator HPALETTE](../Topic/CPalette::operator%20HPALETTE.md)|Retourne `HPALETTE` attaché à `CPalette`.|  
  
## Notes  
 Une palette fournit une interface entre une application et un périphérique de sortie de couleur \(tel qu'un périphérique d'affichage\).  L'interface permet à l'application de profiter pleinement parti des fonctionnalités de couleur du périphérique de sortie sans interférer avec considérablement les couleurs affichées par d'autres applications.  Les fenêtres utilise la palette logique de l'application \(une liste de couleurs nécessaires\) et la palette système \(qui définit des couleurs disponibles\) pour déterminer les couleurs utilisées.  
  
 Un objet d' `CPalette` fournit les fonctions membres pour manipuler la palette référencée par l'objet.  Construisez un objet d' `CPalette` et utilisez ses fonctions membres pour créer la palette réelle, un objet de définition de données \(GDI\) Graphics Device Interface, et pour manipuler ses entrées et d'autres propriétés.  
  
 Pour plus d'informations sur l'utilisation `CPalette`, consultez l' [objets graphiques](../../mfc/graphic-objects.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPalette`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [DIBLOOK exemple MFC](../../top/visual-cpp-samples.md)   
 [CGdiObject Class](../../mfc/reference/cgdiobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPalette::GetPaletteEntries](../Topic/CPalette::GetPaletteEntries.md)   
 [CPalette::SetPaletteEntries](../Topic/CPalette::SetPaletteEntries.md)