---
title: "Param&#232;tres r&#233;gionaux et pages de codes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "jeux de caractères (C++), pages de codes"
  - "jeux de caractères (C++), paramètres régionaux"
  - "pages de codes (C++)"
  - "pages de codes (C++), modifier dynamiquement"
  - "pages de codes (C++), paramètres régionaux"
  - "conventions (C++), prise en charge des caractères internationaux"
  - "ID de paramètres régionaux (C++)"
  - "paramètres régionaux (C++)"
  - "paramètres régionaux (C++), à propos des paramètres régionaux"
  - "localisation (C++), pages de codes"
  - "localisation (C++), paramètres régionaux"
  - "pages de codes multioctets (C++)"
ms.assetid: bd937361-b6d3-4c98-af95-beb7c903187b
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Param&#232;tres r&#233;gionaux et pages de codes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un ID de paramètres régionaux correspond aux conventions et langue locales pour une région géographique spécifique.  Une langue donnée peut être parlée dans plusieurs pays ou régions ; par exemple, le portugais est parlé au Brésil comme au Portugal.  À l'inverse, un pays ou une région peut avoir plusieurs langues officielles.  Par exemple, pour le Canada : l'anglais et le français.  Le Canada dispose donc de deux paramètres régionaux distincts : Anglais \(Canada\) et Français \(Canada\).  Certaines catégories dépendent des paramètres régionaux, notamment la mise en forme des dates et le format d'affichage des valeurs monétaires.  
  
 La langue détermine les conventions de mises en forme des données et du texte, tandis que le pays ou la région détermine les conventions locales.  Chaque langue utilise un mappage unique, représenté par des pages de codes, qui comprend les caractères autres que ceux de l'alphabet \(par exemple, les signes de ponctuation et les nombres\).  Une page de codes est un jeu de caractères et dépend des paramètres régionaux et de la langue.  C'est pourquoi, une [locale](../c-runtime-library/locale.md) est une combinaison unique d'une langue, d'un pays ou d'une région, et d'une page de codes.  Le paramètre de la page de codes peut déterminer les paramètres régionaux et peut être modifié au moment de l'exécution en appelant la fonction [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md).  
  
 Différentes langues peuvent utiliser différentes pages de codes.  Par exemple, la page de codes ANSI 1252 est utilisée par l'anglais et la plupart des langues européennes et la page de codes ANSI 932 est utilisée pour le kanji \(japonais\).  Toutes les pages de codes partagent le jeu de caractères ASCII pour les 128 caractères de bas niveau \(0x00 à 0x7F\).  
  
 Une page de codes codée sur un octet peut être représentée dans un tableau \(à 256 entrées\) sous la forme d'un mappage de valeurs d'octets en caractères \(y compris des nombres et des signes de ponctuation\) ou glyphes.  Toute page de codes multioctets peut également être représentée sous la forme d'un tableau de grande taille \(64K\) de valeurs codées sur deux octets en caractères.  Cependant, en règle générale, elles sont représentées sous la forme d'un tableau pour les 256 premiers caractères \(codé sur un octet\) et sous la forme de plages pour les valeurs codées sur deux octets.  
  
 Pour plus d'informations sur les pages de codes, consultez [Pages de codes](../c-runtime-library/code-pages.md).  
  
 La bibliothèque Runtime C dispose de deux types de pages de codes internes : paramètres régionaux et multioctets.  Vous pouvez changer la page de codes actuelle au cours de l'exécution du programme \(consultez la documentation pour les fonctions [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) et [\_setmbcp](../c-runtime-library/reference/setmbcp.md)\).  De même, la bibliothèque Runtime peut obtenir et utiliser la valeur de la page de codes du système d'exploitation.  Sous Windows 2000, la page de codes du système d'exploitation est la page de codes « ANSI par défaut du système ».  Cette page de codes est constante pour toute la durée de l'exécution du programme.  
  
 Lorsque la page de codes des paramètres régionaux change, le comportement de l'ensemble de fonctions qui en dépend change en fonction de la page de codes choisie.  Par défaut, toutes les fonctions qui dépendent des paramètres régionaux commencent l'exécution avec une page de codes locale unique aux paramètres régionaux « C ».  Vous pouvez changer la page de codes des paramètres régionaux interne \(ainsi que d'autres propriétés spécifiques aux paramètres régionaux\) en appelant la fonction `setlocale`.  Un appel de `setlocale`\(LC\_ALL, ""\) définit les paramètres régionaux à la valeur indiquée par la page de codes par défaut du système d'exploitation.  
  
 De même, lorsque la page de codes multioctets change, le comportement des fonctions multioctets change en fonction de la page de codes choisie.  Par défaut, toutes les fonctions multioctets commencent l'exécution avec une page de codes multioctets qui correspond à la page de codes par défaut du système d'exploitation.  Vous pouvez changer la page de codes multioctets interne en appelant la fonction `_setmbcp`.  
  
 La fonction runtime C `setlocale` définit, change ou interroge les informations de paramètres régionaux du programme actif.  La routine [\_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) est une version à caractère élargi de `setlocale` ; les arguments et les valeurs de retour de `_wsetlocale` sont des chaînes à caractère élargi.  
  
## Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Avantages de la portabilité d'un jeu de caractères](../text/benefits-of-character-set-portability.md)