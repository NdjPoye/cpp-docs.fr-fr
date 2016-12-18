---
title: "Utilisation de wmain au lieu de main | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "wmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "main (fonction), différences par rapport à wmain"
  - "wmain (fonction)"
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de wmain au lieu de main
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Dans le modèle de programmation Unicode, vous pouvez définir une version à caractères larges de la fonction **main**.  Utilisez **wmain** au lieu de **main** si vous souhaitez écrire du code portable conforme à la spécification Unicode.  
  
 Vous déclarez des paramètres formels à **wmain** à l'aide d'un format identique à **main**.  Vous pouvez ensuite passer des arguments à caractère élargi et éventuellement un pointeur d'environnement à caractère élargi au programme.  Les paramètres `argv` et `envp` de la fonction **wmain** sont de type `wchar_t*`.  
  
 Si votre programme utilise une fonction **main**, l'environnement de caractères multioctets est créé par le système d'exploitation au démarrage du programme.  Une copie de l'environnement à caractères larges est créée uniquement lorsqu'elle est nécessaire \(par exemple, par un appel aux fonctions [\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) ou [\_wputenv](../c-runtime-library/reference/putenv-wputenv.md)\).  Au premier appel à `_wputenv`, ou à `_wgetenv` si un environnement MBCS existe déjà, un environnement de chaîne à caractères larges correspondant est créé, puis désigné par la variable globale `_wenviron`, qui est une version à caractères larges de la variable globale `_environ`.  À ce moment\-là, deux copies de l'environnement \(MBCS et Unicode\) existent simultanément et sont conservées par le système d'exploitation pendant toute la vie du programme.  
  
 De même, si votre programme utilise une fonction **wmain**, un environnement MBCS \(ASCII\) est créé à l'occasion du premier appel à `_putenv` ou `getenv`, et désigné par la variable globale `_environ`.  
  
 Pour plus d'informations sur l'environnement MBCS, consultez [Jeux de caractères d'octet unique et multioctets](../c-runtime-library/single-byte-and-multibyte-character-sets.md) dans *Référence de la bibliothèque runtime.*  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)