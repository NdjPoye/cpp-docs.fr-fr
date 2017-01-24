---
title: "Contr&#244;le de type (CRT) | Microsoft Docs"
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
  - "c.types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "contrôler le type"
  - "contrôle de type"
  - "fonctions d'arguments de variable"
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Contr&#244;le de type (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur effectue une vérification de type limitée dans les fonctions pouvant prendre un nombre variable d'arguments, comme suit :  
  
|Appel de fonction|Arguments spécifiques activés|  
|-----------------------|-----------------------------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|Premier argument \(chaîne de format\)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|Les deux arguments \(fichier ou mémoire tampon et chaîne de format\)|  
|`_snprintf_s`|Trois premiers arguments \(fichier ou mémoire tampon, nombre, puis chaîne de format\)|  
|`_open`|Les deux arguments \(chemin d'accès et l'indicateur `_open` \)|  
|`_sopen_s`|Trois premiers arguments \(chemin d'accès, indicateur de `_open`, et mode de partage\)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|Les deux arguments \(chemin d'accès et pointeur premier argument\)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|Trois premiers arguments \(indicateur en mode, le chemin d'accès, et pointeur premier argument\)|  
  
 Le compilateur exécute la même vérification de type limitée dans les homologues de caractères étendus de ces fonctions.  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)