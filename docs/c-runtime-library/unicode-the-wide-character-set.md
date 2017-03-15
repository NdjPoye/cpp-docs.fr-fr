---
title: "Unicode&#160;: jeu de caract&#232;res larges | Microsoft Docs"
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
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Unicode (C++), jeu de caractères larges"
  - "caractères larges (C++), Unicode"
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Unicode&#160;: jeu de caract&#232;res larges
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un caractère élargi est un code de caractère multilingue codé sur deux octets.  La plupart des caractères utilisés en informatique moderne, y compris les symboles techniques et les caractères de publication spéciaux, peuvent être représentés en fonction de la spécification Unicode en tant que caractère élargi.  Développé et géré par un grand consortium, qui inclut Microsoft, la norme Unicode est maintenant largement utilisée.  
  
 Un caractère large est de type `wchar_t`.  Une chaîne de caractère larges est représentée sous la forme d'un tableau `wchar_t[]` vers lequel un pointeur `wchar_t*` pointe.  Tout caractère ASCII peut être représenté en tant que caractère élargi en ajoutant la lettre `L` avant le caractère.  Par exemple, L'\\0' est le caractère de fin \(16 bits\) `NULL` .  De même, toute chaine de type littéral ASCII peut être représenté en tant que chaine de type littéral à caractère élargi en ajoutant la lettre L avant le littéral ASCII \(L"Hello"\).  
  
 En règle générale, les caractères élargis prennent plus d'espace en mémoire que les caractères multioctets mais sont plus rapides à traiter.  De plus, seul un paramètre régional peut être représenté en même temps dans un encodage multioctets, alors que tous les jeux de caractères du monde sont représentés en même temps par la représentation Unicode.  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)