---
title: "Espace de noms stdext | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_DEFINE_DEPRECATED_HASH_CLASSES (symbole)"
  - "stdext, espace de noms"
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Espace de noms stdext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les membres des fichiers d’en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et [\<hash\_set\>](../standard-library/hash-set.md) ne font pas actuellement pas partie de la norme C\+\+ ISO. Par conséquent, ces types et ces membres ont été déplacés de l’espace de noms `std` vers l’espace de noms `stdext`, de façon à rester conforme à la norme C\+\+.  
  
 Lors de la compilation avec [\/Ze](../build/reference/za-ze-disable-language-extensions.md), qui est la valeur par défaut, le compilateur vous avertit de l’utilisation de `std` pour les membres des fichiers d’en\-tête \<hash\_map\> et \<hash\_set\>. Pour désactiver l’avertissement, utilisez le pragma [warning](../preprocessor/warning.md).  
  
 Pour que le compilateur génère une erreur pour l’utilisation de `std` pour les membres des fichiers d’entête \<hash\_map\> et \<hash\_set\> avec **\/Ze**, ajoutez la directive suivante avant d’inclure les fichiers d’en\-tête de la bibliothèque C\+\+ standard.  
  
```  
#define _DEFINE_DEPRECATED_HASH_CLASSES 0  
```  
  
 Lors de la compilation avec **\/Za**, le compilateur génère une erreur.  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)