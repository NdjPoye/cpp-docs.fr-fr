---
title: "Texte et cha&#238;nes en Visual C++ | Microsoft Docs"
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
helpviewer_keywords: 
  - "caractères ASCII (C++)"
  - "jeux de caractères (C++)"
  - "jeux de caractères (C++), à propos des jeux de caractères"
  - "jeux de caractères (C++), non européens"
  - "globalisation (C++)"
  - "globalisation (C++), jeux de caractères"
  - "applications internationales (C++), à propos des applications internationales"
  - "caractères japonais (C++)"
  - "caractères Kanji (prise en charge) (C++)"
  - "jeux de caractères locaux (C++)"
  - "localisation (C++)"
  - "localisation (C++), jeux de caractères"
  - "MBCS (C++), programmation internationale"
  - "prise en charge multilingue (C++)"
  - "caractères non européens (C++)"
  - "portabilité (C++)"
  - "portabilité (C++), jeux de caractères"
  - "programmation (C++), international"
  - "traduire du code (C++)"
  - "conversion (C++), jeux de caractères"
  - "Unicode (C++)"
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: 12
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Texte et cha&#238;nes en Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un aspect important du développement d'applications pour les marchés internationaux est la représentation adéquate des jeux de caractères locaux.  Le jeu de caractères ASCII définit les caractères de la plage 0x00 à 0x7F.  Il existe d'autres jeux de caractères, par exemple le jeu de caractères européen, qui définissent les caractères de la plage 0x00 à 0x7F de la même façon que le jeu de caractères ASCII et qui définissent également un jeu de caractères étendus de 0x80 à 0xFF.  C'est pourquoi, un jeu de caractères codé sur un octet \(SBCS\), 8 bits, est suffisant pour représenter le jeu de caractères ASCII, ainsi que les jeux de caractères pour de nombreuses langues européennes.  Cependant, certains jeux de caractères pour des langues non européennes, par exemple le kanji japonais, comprennent beaucoup plus de caractères que ceux que peut représenter un schéma d'encodage sur un octet et nécessitent un encodage de jeu de caractères multioctets \(MBCS\).  
  
## Dans cette section  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)  
 Décrit la prise en charge de la programmation Unicode et MBCS par Visual C\+\+.  
  
 [Prise en charge pour Unicode](../text/support-for-unicode.md)  
 Unicode est une spécification pour la prise en charge des jeux de caractères, y compris les jeux de caractères qui ne peuvent pas être représentés par un seul octet.  
  
 [Prise en charge pour les jeux de caractères multioctets \(MBCS\)](../text/support-for-multibyte-character-sets-mbcss.md)  
 Les jeux de caractères multioctets \(MBCS\) peuvent remplacer Unicode pour la prise en charge des jeux de caractères, tels que les jeux de caractères japonais et chinois, qui ne peuvent pas être représentés par un seul octet.  
  
 [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md)  
 Fournit des mappages de texte générique spécifiques à Microsoft pour de nombreux types de données, routines et autres objets.  
  
 [Comment : effectuer une conversion entre différents types de chaînes](../text/how-to-convert-between-various-string-types.md)  
 Explique comment convertir divers types de chaînes Visual C\+\+ en d'autres chaînes.  
  
## Rubriques connexes  
 [Internationalisation](../c-runtime-library/internationalization.md)  
 Décrit la prise en charge internationale dans la bibliothèque Runtime C.  
  
 [Exemples internationaux](http://msdn.microsoft.com/fr-fr/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Fournit des liens vers des exemples illustrant l'utilisation de l'internationalisation dans Visual C\+\+.  
  
 [Chaînes relatives à la langue, au pays et à la région](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 Fournit les chaînes pour la langue et le pays ou la région dans la bibliothèque Runtime C.