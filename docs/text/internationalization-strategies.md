---
title: "Stratégies d’internationalisation | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b7ab27bb7a6458efde84451febaeb6f3ef37115
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="internationalization-strategies"></a>Stratégies d'internationalisation
En fonction de vos systèmes d’exploitation cibles et les marchés, vous disposez de plusieurs stratégies d’internationalisation :  
  
-   Votre application utilise Unicode et par conséquent s’exécute sur Windows 2000 et Windows NT, mais pas sur Windows 95 ou Windows 98.  
  
     Vous utilisez des fonctionnalités spécifique à Unicode et tous les caractères sont de 16 bits (bien que vous pouvez utiliser des caractères ANSI dans certaines parties de votre programme à des fins spéciales). La bibliothèque Runtime C fournit des fonctions, macros et types de données pour la programmation Unicode uniquement. MFC est entièrement compatible Unicode.  
  
-   Votre application utilise MBCS et peut être exécutée sur n’importe quelle plateforme Win32.  
  
     Vous utilisez des fonctionnalités propres à MBCS. Chaînes peuvent contenir des caractères codés sur un octet, les caractères codés sur deux octets ou les deux. La bibliothèque Runtime C fournit des fonctions, macros et types de données pour la programmation MBCS uniquement. MFC est entièrement compatible MBCS.  
  
-   Le code source pour votre application est écrit pour une portabilité totale, en recompilant avec le symbole **_UNICODE** ou le symbole **_MBCS** défini, vous pouvez produire des versions qui utilisent l’un. Pour plus d’informations, consultez [des mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Votre application utilise une bibliothèque de wrappers pour les fonctions Unicode manquantes sur Windows 95, Windows 98 et Windows ME comme celle qui est décrite dans [concevoir une application Unicode unique qui s’exécute à la fois Windows 98 et Windows 2000](http://go.microsoft.com/fwlink/p/?LinkId=250770). Les bibliothèques de wrappers sont également disponibles dans le commerce.  
  
     Vous utilisez entièrement portables C Runtime fonctions, macros et types de données. La flexibilité MFC prend en charge ces stratégies.  
  
 Le reste de ces rubriques vous concentrer sur l’écriture de code portable que vous pouvez générer en Unicode ou en MBCS.  
  
## <a name="see-also"></a>Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Paramètres régionaux et pages de codes](../text/locales-and-code-pages.md)