---
title: "E/S de fichier en mode texte et binaire | Microsoft Docs"
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
  - "accès binaire"
  - "accès binaire, E/S de fichier en mode binaire"
  - "fichiers (C++), open (fonctions)"
  - "fonctions (CRT), accès au fichier"
  - "E/S (CRT), binaire"
  - "E/S (CRT), fichiers texte"
  - "E/S (CRT), modes de translation"
  - "fichiers texte, E/S"
  - "modes de translation (E/S de fichier)"
  - "translation, modes"
ms.assetid: 3196e321-8b87-4609-b302-cd6f3c516051
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# E/S de fichier en mode texte et binaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérations d'E\/S sont lieu dans l'un des deux modes de traduction, texte ou binaire, selon le mode dans lequel le fichier est ouvert.  Les fichiers de données sont généralement traités en mode texte.  Pour contrôler le fichier en mode de traduction, on peut :  
  
-   Conserver le paramètre par défaut actuel et spécifier l'autre mode uniquement lorsque vous ouvrez des fichiers sélectionnés.  
  
-   Utilisez la fonction [\_set\_fmode](../c-runtime-library/reference/set-fmode.md) pour modifier le mode par défaut des fichiers ouverts récemment.  Utilisez [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) pour rechercher le mode par défaut actuel.  Le paramètre par défaut initial est mode texte \(`_O_TEXT`\).  
  
-   Modifiez le type de mode de traduction par défaut directement en définissant la variable globale [\_fmode](../c-runtime-library/fmode.md) dans votre programme.  La fonction `_set_fmode` définit la valeur de cette variable, mais elle peut également être définie directement.  
  
 Lorsque vous appelez une fonction de type FILE\- OPEN par exemple [\_open](../c-runtime-library/reference/open-wopen.md), [fopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md), [freopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md), [\_fsopen](../c-runtime-library/reference/fsopen-wfsopen.md) ou [\_sopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md), vous pouvez remplacer la valeur par défaut actuelle de `_fmode` en spécifiant l'argument approprié pour la fonction [\_set\_fmode](../c-runtime-library/reference/set-fmode.md).  `stdin`, `stdout`, et les flux `stderr` s'ouvrent toujours en mode texte par défaut ; vous pouvez également remplacer cette valeur par défaut lors de l'ouverture de l'un de ces fichiers.  Utilisez [\_setmode](../c-runtime-library/reference/setmode.md) pour modifier le type de mode de traduction dans le descripteur de fichier lorsque le fichier est ouvert.  
  
## Voir aussi  
 [Entrées et sorties](../c-runtime-library/input-and-output.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)