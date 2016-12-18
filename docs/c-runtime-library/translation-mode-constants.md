---
title: "Constantes de mode de translation | Microsoft Docs"
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
  - "_O_BINARY"
  - "_O_TEXT"
  - "_O_RAW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_BINARY (constante)"
  - "_O_RAW (constante)"
  - "_O_TEXT (constante)"
  - "O_BINARY (constante)"
  - "O_RAW (constante)"
  - "O_TEXT (constante)"
  - "constantes de translation"
  - "modes de translation (E/S de fichier)"
  - "translation, constantes"
  - "translation, modes"
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Constantes de mode de translation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Notes  
 Les constantes manifestes `_O_BINARY` et `_O_TEXT` déterminent le mode de traduction pour les fichiers \(`_open` et `_sopen`\) ou le mode de traduction pour les flux de données \(`_setmode`\).  
  
 Les valeurs autorisées sont :  
  
 `_O_TEXT`  
 Ouvre un fichier en mode texte \(traduit\).  Les combinaisons sauts de ligne\-retour de chariot \(CR\-LF\) sont traduites en un unique caractère de saut de ligne en entrée.  Les caractères de saut de ligne sont convertis en combinaisons CR\-LF en sortie.  En outre, CTRL\+Z est interprété comme caractère de fin de fichier sur l'entrée.  Dans les fichiers ouverts en lecture et en lecture\/écriture, `fopen` vérifie la présence de Ctrl\+Z à la fin du fichier et le supprime, si possible.  Cette opération est effectuée car l'utilisation des fonctions `fseek` et `ftell` pour se déplacer dans un fichier qui se termine par Ctrl\+Z peut provoquer un comportement incorrect de `fseek` près de la fin du fichier.  
  
 `_O_BINARY`  
 Ouvre le fichier en mode \(non traduit\) binaire.  Les traductions ci\-dessus sont supprimées.  
  
 `_O_RAW`  
 Identique à `_O_BINARY`.  Pris en charge pour la compatibilité C 2,0.  
  
 Pour plus d'informations, consultez [E\/S de fichier en mode texte et binaire](../c-runtime-library/text-and-binary-mode-file-i-o.md) et [File Translation](../c-runtime-library/file-translation-constants.md).  
  
## Voir aussi  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_pipe](../c-runtime-library/reference/pipe.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_setmode](../c-runtime-library/reference/setmode.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)