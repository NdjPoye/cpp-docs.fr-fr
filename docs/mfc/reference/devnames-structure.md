---
title: "DEVNAMES, structure | Microsoft Docs"
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
  - "DEVNAMES"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DEVNAMES"
ms.assetid: aac97f60-2169-471a-ba5d-c0baed9eed9a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DEVNAMES, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `DEVNAMES` contient des chaînes qui identifient le pilote, le périphérique, et les noms de port de sortie pour une imprimante.  
  
## Syntaxe  
  
```  
  
      typedef struct tagDEVNAMES { /* dvnm */  
    WORD wDriverOffset;  
    WORD wDeviceOffset;  
    WORD wOutputOffset;  
    WORD wDefault;  
    /* driver, device, and port-name strings follow wDefault */  
} DEVNAMES;  
```  
  
#### Paramètres  
 *wDriverOffset*  
 \(Entrée\/sortie\) spécifie le décalage de caractères dans une chaîne terminée par le caractère NULL qui contient le nom de fichier \(sans l'extension\) du pilote de périphérique.  En entrée, cette chaîne est utilisée pour déterminer l'imprimante à s'afficher initialement dans la boîte de dialogue.  
  
 *wDeviceOffset*  
 \(Entrée\/sortie\) spécifie le décalage en caractères vers la chaîne terminée par le caractère NULL \(maximum de 32 octets incluant NULL\) qui contient le nom du périphérique.  Cette chaîne doit être identique au membre **dmDeviceName** de la structure [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565).  
  
 *wOutputOffset*  
 \(Entrée\/sortie\) spécifie le décalage en caractères vers la chaîne terminée par le caractère NULL qui contient le nom de l'unité de restauration pour le support de sortie physique \(port de sortie\).  
  
 *wDefault*  
 Spécifie si les chaînes contenues dans la structure `DEVNAMES` identifient l'imprimante par défaut.  Cette chaîne est utilisée pour vérifier que l'imprimante par défaut n'a pas changé depuis la dernière opération d'impression.  En entrée, si l'indicateur **DN\_DEFAULTPRN** est défini, les valeurs de la structure `DEVNAMES` sont vérifiées par rapport à l'imprimante par défaut actuelle.  Si l'une des chaînes ne correspond pas, un message d'avertissement est affiché qui informe l'utilisateur que le document doit être remanié.  En sortie, le membre **wDefault** n'est modifié que si la boîte de dialogue de configuration de l'impression est affichée et l'utilisateur choisit le bouton OK.  L'indicateur **DN\_DEFAULTPRN** est défini si l'imprimante par défaut est sélectionnée.  Si une imprimante spécifique est sélectionnée, l'indicateur n'est pas défini.  Tous les bits de ce membre sont réservés à un usage interne par la procédure de la boîte de dialogue Imprimer.  
  
## Notes  
 La fonction **PrintDlg** utilise ces chaînes pour initialiser les membres dans la boîte de dialogue Imprimer définie par le système.  Lorsque l'utilisateur ferme la boîte de dialogue, les informations sur l'imprimante sélectionnée sont retournées dans cette structure.  
  
## Configuration requise  
 **En\-tête :** commdlg.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPrintDialog::CreatePrinterDC](../Topic/CPrintDialog::CreatePrinterDC.md)