---
title: "Conformit&#233; ANSI C | Microsoft Docs"
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
  - "Ansi"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ANSI (C++), standard C"
  - "compatibilité (C++), C ANSI"
  - "conformité avec C ANSI"
  - "conventions (C++), extensions Microsoft"
  - "conventions d'affectation de noms des extensions Microsoft"
  - "conventions d'affectation de noms (C++), bibliothèque Microsoft"
  - "caractères de soulignement"
  - "caractères de soulignement, interligne"
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conformit&#233; ANSI C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La convention d'affectation des noms pour les identificateurs spécifiques à Microsoft dans le système run\-time \(par exemple les fonctions, les macros, les constantes, les variables, et les définitions de type\) est conforme à l'ANSI.  Dans cette documentation, toute fonction run\-time qui suit les normes ANSI\/ISO C est notée comme étant compatible ANSI.  Les applications conformes à l'ANSI qui doivent utiliser uniquement ces fonctions compatibles ANSI.  
  
 Les noms des fonctions et des variables globales spécifiques à Microsoft commencent par un unique tiret bas.  Ces noms peuvent être substitués uniquement localement, dans le cadre de votre code.  Par exemple, lorsque vous incorporez les fichiers d'en\-tête de l'exécution de Microsoft, vous pouvez néanmoins localement remplacer la fonction spécifique à Microsoft nommée `_open` en déclarant une variable locale du même nom.  Toutefois, vous ne pouvez pas utiliser ce nom pour votre propre fonction globale ou variable globale.  
  
 Les noms de macros spécifiques à Microsoft et les constantes manifestes commencent par deux tirets bas, ou par un tiret bas suivi d'une lettre majuscule.  L'étendue des identificateurs est absolue.  Par exemple, vous ne pouvez pas utiliser l'identificateur **\_UPPER** spécifique à Microsoft par conséquent.  
  
## Voir aussi  
 [Compatibilité](../c-runtime-library/compatibility.md)