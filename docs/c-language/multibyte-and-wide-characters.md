---
title: "Multioctets et caract&#232;res larges | Microsoft Docs"
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
  - "codes de caractères (C++), multioctets"
  - "codes de caractères (C++), larges"
  - "types de données caractère (C)"
  - "caractères (C++), codes"
  - "caractères (C++), larges"
  - "globalisation (C++), jeux de caractères"
  - "applications internationales (C++), affichage des caractères"
  - "caractères multioctets (C++)"
  - "types (C), caractère"
  - "Unicode (C++), jeu de caractères larges"
  - "caractères larges (C++)"
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multioctets et caract&#232;res larges
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un caractère multioctet est un caractère composé de séquences d'un ou plusieurs octets.  Chaque séquence d'octets représente un caractère unique dans le jeu de caractères étendu.  Les caractères multioctets sont utilisés dans les jeux de caractères tels que Kanji.  
  
 Les caractères larges sont des codes de caractères multilingues qui ont toujours une largeur de 16 bits.  Le type des constantes caractères est `char`. Pour les caractères larges, le type est `wchar_t`.  Comme les caractères larges ont toujours une taille fixe, leur utilisation simplifie la programmation avec les jeux de caractères internationaux.  
  
 Le littéral de chaîne à caractères larges `L"hello"` devient un tableau de six entiers de type `wchar_t`.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 La spécification Unicode régit les caractères larges.  Les routines de bibliothèque Runtime permettant de traduire des caractères multioctets et larges incluent `mbstowcs`, `mbtowc`, `wcstombs` et `wctomb`.  
  
## Voir aussi  
 [Identificateurs C](../c-language/c-identifiers.md)