---
title: "_fmode | Microsoft Docs"
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
  - "fmode"
  - "_fmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "traduction de fichiers [C++], mode par défaut"
  - "fmode (fonction)"
  - "_fmode (fonction)"
ms.assetid: ac6df9eb-e5cc-4c54-aff3-373c21983118
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La variable `_fmode` définit le mode de traduction de fichier par défaut pour le texte ou la traduction binaire.  Cette variable globale a été déconseillée pour les versions fonctionnelles plus sécurisées [\_get\_fmode](../c-runtime-library/reference/get-fmode.md) et [\_set\_fmode](../c-runtime-library/reference/set-fmode.md), qui doivent être utilisées à la place de la variable globale.  Il est déclaré dans Stdlib.h comme suit.  
  
## Syntaxe  
  
```  
extern int _fmode;  
```  
  
## Notes  
 Le paramètre par défaut de `_fmode` est `_O_TEXT` pour la traduction de mode texte.  `_O_BINARY` est le paramètre pour le mode binaire.  
  
 Vous pouvez modifier la valeur de `_fmode` de trois manières :  
  
-   Lien avec Binmode.obj.  Cela modifie le paramètre initial de `_fmode` à `_O_BINARY`, ce qui fait que tous les fichiers sauf `stdin`, `stdout`, et `stderr` s'ouvrent en mode binaire.  
  
-   Effectuez un appel à `_get_fmode` ou à `_set_fmode` pour obtenir ou définir la variable globale `_fmode`, respectivement.  
  
-   Modifiez la valeur de `_fmode` directement en la définissant dans votre programme.  
  
## Voir aussi  
 [Variables globales](../c-runtime-library/global-variables.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)