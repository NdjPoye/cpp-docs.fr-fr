---
title: "Constantes d&#39;attributs de fichier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A_HIDDEN"
  - "_A_NORMAL"
  - "_A_SUBDIR"
  - "_A_RDONLY"
  - "A_NORMAL"
  - "A_SUBDIR"
  - "_A_SYSTEM"
  - "c.constants.file"
  - "_A_HIDDEN"
  - "A_RDONLY"
  - "_A_ARCH"
  - "A_ARCH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_A_ARCH (constante)"
  - "_A_HIDDEN (constante)"
  - "_A_NORMAL (constante)"
  - "_A_RDONLY (constante)"
  - "_A_SUBDIR (constante)"
  - "_A_SYSTEM (constante)"
  - "constantes (C++), attributs de fichiers"
  - "constantes d'attributs de fichier (C++)"
  - "fichiers (C++), constantes d'attributs de fichier"
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Constantes d&#39;attributs de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
#include <io.h>  
```  
  
## Notes  
 Ces constantes spécifient les attributs actuels du fichier ou du répertoire spécifié par la fonction.  
  
 Les attributs sont représentés par les constantes manifestes suivantes :  
  
 `_A_ARCH`  
 Archive.  Définissez chaque fois que le fichier est modifié, et désactivé par la Commande BACKUP.  Valeur : 0x20  
  
 `_A_HIDDEN`  
 fichiers masqués  Généralement pas vus avec la commande de DIR, à moins que l'option \/AH est utilisée.  Retourne des informations sur les fichiers normaux ainsi que les fichiers avec cet attribut.  Valeur : 0x02  
  
 `_A_NORMAL`  
 Normal.  Le fichier puisse être lu ou écrit sans restriction.  Valeur : 0x00  
  
 `_A_RDONLY`  
 En lecture seule.  Impossible d'ouvrir le fichier en écriture, et un fichier portant le même nom ne peut pas être créé.  Valeur : 0x01  
  
 `_A_SUBDIR`  
 Sous\-répertoire.  Valeur : 0x10  
  
 `_A_SYSTEM`  
 Fichier système.  Généralement pas vus avec la commande de DIR, à moins que l'option \/AS soit utilisée.  Valeur : 0x04  
  
 Plusieurs constantes peuvent être associées à l'opérateur OR \(&#124;\).  
  
## Voir aussi  
 [Fonctions de recherche de nom de fichier](../c-runtime-library/filename-search-functions.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)