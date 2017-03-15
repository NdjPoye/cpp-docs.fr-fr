---
title: "Erreurs de position de fichier | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "pointeurs de fichier (C++), erreurs de position de fichier"
ms.assetid: d5e59d8b-08c0-4927-a338-0b2d8234ce24
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Erreurs de position de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.9.9.1, 4.9.9.4** Valeur à laquelle la macro `errno` est définie par la fonction `fgetpos` ou `ftell` en cas d'échec  
  
 Lorsque `fgetpos` ou `ftell` échoue, `errno` prend comme valeur la constante de manifeste `EINVAL` si la position est non valide ou EBADF si le numéro de fichier est incorrect.  Les constantes sont définies dans ERRNO.H.  
  
## Voir aussi  
 [Fonctions des bibliothèques](../c-language/library-functions.md)