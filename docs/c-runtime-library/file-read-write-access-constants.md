---
title: "Constantes d&#39;acc&#232;s fichier en lecture/&#233;criture | Microsoft Docs"
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
  - "c.constants.file"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "constantes d'accès pour lire et écrire dans un fichier"
  - "constantes (C++), attributs de fichiers"
  - "constantes d'accès pour lire et écrire dans un fichier"
  - "constantes d'accès pour lire et écrire"
  - "constantes d'accès pour écrire"
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes d&#39;acc&#232;s fichier en lecture/&#233;criture
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <stdio.h>  
```  
  
## Notes  
 Ces constantes spécifient le type d'accès \(« a », « r », ou « W »\) demandé pour le fichier.  Le [mode de traduction](../c-runtime-library/file-translation-constants.md) \(« b » ou « t »\) et le [mode de validation sur disque](../c-runtime-library/commit-to-disk-constants.md) \(« c » ou « n »\) peuvent être spécifiés avec le type d'accès.  
  
 Les types d'accès sont décrits ci\-dessous.  
  
 **"a"**  
 S'ouvre pour écrire à la fin du fichier \(ajouter\) ; crée le fichier d'abord s'il n'existe pas.  Toutes les opérations d'écriture se produisent à la fin du fichier.  Même si le pointeur de fichier peut être repositionné à l'aide de `fseek` or **rewind**, il est toujours redéplacé à la fin du fichier avant toute opération d'écriture.  
  
 **"a\+"**  
 Comme ci\-dessus, mais autorise également la lecture.  
  
 **"r"**  
 Ouvre pour l'accès en lecture.  Si le fichier n'existe pas ou est introuvable, l'appel pour ouvrir le fichier échouera.  
  
 **"r\+"**  
 Ouvre pour l'accès en lecture et en écriture.  Si le fichier n'existe pas ou est introuvable, l'appel pour ouvrir le fichier échouera.  
  
 **"w"**  
 Ouvre un fichier vide pour l'accès en écriture.  Si le fichier spécifié existe, son contenu est détruit.  
  
 **"w\+"**  
 Ouvre un fichier vide pour l'accès en lecture et en écriture.  Si le fichier spécifié existe, son contenu est détruit.  
  
 Lorsque le type "r\+", "w\+", ou "a\+"   est spécifié, la lecture et l'écriture sont autorisées \(on dit que le fichier est ouvert pour « mise à jour »\).  Toutefois, lorsque vous basculez entre la lecture et l'écriture, il doit y avoir une intervention de `fflush`, `fsetpos`, `fseek`, ou une opération **rewind** .  La position actuelle peut être spécifiée pour une opération `fsetpos` ou de `fseek`.  
  
## Voir aussi  
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)