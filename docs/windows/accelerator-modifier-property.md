---
title: "Modifier, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Modifier (propriété)"
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifier, propri&#233;t&#233; d&#39;un acc&#233;l&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous trouverez ci\-dessous les entrées valides pour la propriété Modifier dans la table d'accélérateurs.  
  
|Valeur|Description|  
|------------|-----------------|  
|**Aucun**|L'utilisateur appuie uniquement sur la valeur de touche.  Valeur utilisée avec les valeurs ASCII\/ANSI 001 à 026, ce qui correspond à ^A à ^Z \(CTRL\-A à CTRL\-Z\).|  
|**Alt**|L'utilisateur doit appuyer sur la touche ALT avant la valeur de la touche.|  
|**Ctrl**|L'utilisateur doit appuyer sur la touche CTRL avant la valeur de la touche.  Non valide avec le type ASCII.|  
|**Shift**|L'utilisateur doit appuyer sur la touche MAJ avant la valeur de la touche.|  
|**Ctrl\+Alt**|L'utilisateur doit appuyer sur la touche CTRL et la touche ALT avant la valeur de la touche.  Non valide avec le type ASCII.|  
|**Ctrl\+Maj**|L'utilisateur doit appuyer sur la touche CTRL et la touche MAJ avant la valeur de la touche.  Non valide avec le type ASCII.|  
|**Alt\+Maj**|L'utilisateur doit appuyer sur la touche ALT et la touche MAJ avant la valeur de la touche.  Non valide avec le type ASCII.|  
|**Ctrl\+Alt\+Maj**|L'utilisateur doit appuyer sur les touches CTRL, ALT et MAJ avant la valeur de la touche.  Non valide avec le type ASCII.|  
  
## Configuration requise  
 Win32  
  
## Voir aussi  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)