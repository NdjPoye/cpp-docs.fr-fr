---
title: "PAINTSTRUCT, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PAINTSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PAINTSTRUCT (structure)"
ms.assetid: 81ce4993-3e89-43b2-8c98-7946f1314d24
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PAINTSTRUCT, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `PAINTSTRUCT` contient des informations qui peuvent être utilisés pour peindre la zone client d'une fenêtre.  
  
## Syntaxe  
  
```  
  
      typedef struct tagPAINTSTRUCT {  
   HDC hdc;  
   BOOL fErase;  
   RECT rcPaint;  
   BOOL fRestore;  
   BOOL fIncUpdate;  
   BYTE rgbReserved[16];  
} PAINTSTRUCT;  
```  
  
#### Paramètres  
 *hdc*  
 Identifie le contexte d'affichage à utiliser pour la peinture.  
  
 *fErase*  
 Spécifie si l'arrière\-plan doit être repeint.  Ca ne vaut pas nul si l'application doit redessiner l'arrière\-plan.  L'application est responsable de dessiner l'arrière\-plan si une classe de fenêtre Windows est créée sans pinceau d'arrière\-plan \(consultez la description du membre **hbrBackground** de la structure [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]\).  
  
 *rcPaint*  
 Spécifie le coin supérieur gauche et inférieur droit du rectangle dans lequel la peinture est demandée.  
  
 *fRestore*  
 membre réservé.  Il est utilisé en interne par Windows.  
  
 *fIncUpdate*  
 membre réservé.  Il est utilisé en interne par Windows.  
  
 *rgbReserved \[16\]*  
 membre réservé.  Un bloc de mémoire réservée utilisée en interne par Windows.  
  
## Configuration requise  
 **En\-tête :** winuser.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPaintDC::m\_ps](../Topic/CPaintDC::m_ps.md)