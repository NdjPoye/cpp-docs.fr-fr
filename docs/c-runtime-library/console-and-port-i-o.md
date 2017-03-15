---
title: "Console et port E/S | Microsoft Docs"
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
  - "c.io"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E/S (CRT), console"
  - "E/S (CRT), port"
  - "routines E/S, E/S de console et de port"
  - "ports, routines E/S"
  - "routines"
  - "routines, E/S de console et de port"
ms.assetid: 0eee1c92-9b3d-41e0-a43a-257e546eeec8
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Console et port E/S
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces routines lisent et écrivent sur la console ou sur le port spécifié.  Les routines d'E\/S de console ne sont pas compatibles avec les E\/S de flux ou les routines de bibliothèque de bas niveau d'E\/S.  La console ou le port ne doit être ouvert ou fermé avant que les E\/S soit exécutée, il n'y a pas de routine ouverte ou proche de cette catégorie.  Dans les systèmes d'exploitation Windows, la sortie de ces fonctions sont toujours dirigée vers la console et ne peut pas être redirigés.  
  
### Console et port E\/S  
  
|Routine|Utilisez|  
|-------------|--------------|  
|[\_cgets, \_cgetws](../c-runtime-library/cgets-cgetws.md), [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|Chaîne de console|  
|[\_cprintf, \_cwprintf](../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md), [\_cprintf\_s, \_cprintf\_s\_l, \_cwprintf\_s, \_cwprintf\_s\_l](../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)|Écrire des données mises en forme dans une console.|  
|[\_cputs](../c-runtime-library/reference/cputs-cputws.md)|Ecrire une chaîne en console|  
|[\_cscanf, \_cwscanf](../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md), [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)|Données mises en forme de la console|  
|[\_getch, \_getwch](../c-runtime-library/reference/getch-getwch.md)|Lire un caractère de la console|  
|[\_getche, \_getwche](../c-runtime-library/reference/getch-getwch.md)|Lisez le caractère de la console et le faites un écho|  
|[\_inp](../c-runtime-library/inp-inpw-inpd.md)|Lire un octet de port d'E\/S spécifié|  
|[\_inpd](../c-runtime-library/inp-inpw-inpd.md)|Double mot de port d'E\/S spécifié|  
|[\_inpw](../c-runtime-library/inp-inpw-inpd.md)|Lecture mot de 2 octets de port d'E\/S spécifié|  
|[\_kbhit](../c-runtime-library/reference/kbhit.md)|Contrôle de la combinaison de touches à la console ; utilisez avant d'essayer de lire à partir de la console|  
|[\_outp](../c-runtime-library/outp-outpw-outpd.md)|Écrire un octet au port d'E\/S spécifié|  
|[\_outpd](../c-runtime-library/outp-outpw-outpd.md)|Double mot d'écriture au port d'E\/S spécifié|  
|[\_outpw](../c-runtime-library/outp-outpw-outpd.md)|Double mot d'écriture au port d'E\/S spécifié|  
|[\_putch, \_putwch](../c-runtime-library/reference/putch-putwch.md)|Ecrire un caractère en console|  
|[\_ungetch, \_ungetwch](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)|La dernière lecture de caractère « Unget » de la console pour qu'elle devient lecture suivante de caractères|  
  
## Voir aussi  
 [Entrées et sorties](../c-runtime-library/input-and-output.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)