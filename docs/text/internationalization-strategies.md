---
title: "Strat&#233;gies d&#39;internationalisation | Microsoft Docs"
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
  - "jeux de caractères (C++), stratégies de programmation internationale"
  - "globalisation (C++), jeux de caractères"
  - "code portable dans différents langages"
  - "localisation (C++), jeux de caractères"
  - "MBCS (C++), stratégies d'internationalisation"
  - "Unicode (C++), globaliser les applications"
  - "Win32 (C++), stratégies de programmation internationale"
  - "API Windows (C++), stratégies de programmation internationale"
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Strat&#233;gies d&#39;internationalisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En fonction des systèmes d'exploitation et des marchés cibles, vous disposez de plusieurs stratégies d'internationalisation :  
  
-   Votre application utilise Unicode et par conséquent, s'exécute sous Windows 2000, mais pas sous Windows 95 ou Windows 98.  
  
     Vous utilisez l'ajout de fonctionnalités spécifique à Unicode et tous les caractères sont de 16 bits \(bien que vous puissiez utiliser les caractères ANSI dans certaines parties de votre programme à des fins spécifiques\).  La bibliothèque Runtime C fournit des fonctions, des macros et des types de données pour la programmation Unicode uniquement.  MFC est entièrement compatible Unicode.  
  
-   Votre application utilise MBCS et peut être exécutée sur n'importe quelle plateforme Win32.  
  
     Vous utilisez l'ajout de fonctionnalités spécifique à MBCS.  Les chaînes peuvent contenir des caractères codés sur un octet, des caractères codés sur deux octets, ou les deux.  La bibliothèque Runtime C fournit des fonctions, des macros et des types de données pour la programmation MBCS uniquement.  MFC est entièrement compatible MBCS.  
  
-   Le code source pour votre application est écrit pour une portabilité totale, en recompilant avec le symbole **\_UNICODE** ou le symbole **\_MBCS** défini, vous pouvez produire des versions qui utilisent l'un ou l'autre.  Pour plus d'informations, consultez [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Votre application utilise une bibliothèque de wrappers pour les fonctions Unicode manquantes sur Windows 95, Windows 98 et Windows ME comme celle décrite dans [Design a Single Unicode App that Runs on Both Windows 98 and Windows 2000 \(en anglais\)](http://go.microsoft.com/fwlink/p/?LinkId=250770).  Les bibliothèques de wrappers sont également disponibles dans le commerce.  
  
     Vous utilisez des fonctions, des macros et des types de données runtime C entièrement portables.  La flexibilité MFC prend en charge ces stratégies.  
  
 Le reste de ces rubriques traite de l'écriture de code portable que vous pouvez générer en Unicode ou en MBCS.  
  
## Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Paramètres régionaux et pages de codes](../text/locales-and-code-pages.md)