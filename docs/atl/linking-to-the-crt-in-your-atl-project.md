---
title: "Linking to the CRT in Your ATL Project | Microsoft Docs"
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
  - "DllMainCRTStartup"
  - "wWinMainCRTStartup"
  - "WinMainCRTStartup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, C Run-Time library (CRT)"
  - "CRT, linking with ATL"
  - "DllMainCRTStartup method"
  - "WinMainCRTStartup method"
  - "wWinMainCRTStartup method"
ms.assetid: 650957ae-362c-4ecf-8b03-5d49138e8b5b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Linking to the CRT in Your ATL Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Bibliothèques runtime C](../c-runtime-library/crt-library-features.md) \(CRT\) fournissent de nombreuses fonctions utiles peuvent rendre programmer beaucoup plus facile pendant le développement ATL.  Tous les projets ATL sont liés à la bibliothèque CRT.  Vous pouvez consulter les avantages et les inconvénients de joindre la méthode dans [Avantages et compromis de la méthode utilisée à lier au CRT](../atl/benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt.md).  
  
## Effets de lier au CRT sur votre image de programme  
 Si vous liez de manière statique au CRT, le code du CRT est défini dans votre image exécutable et vous n'avez pas besoin d'avoir la DLL CRT présent sur un système d'exécuter votre image.  Si vous liez dynamiquement au CRT, les références au code dans la DLL CRT ne sont définies dans votre image, mais pas le code lui\-même.  Pour que votre image s'exécute sur un système donné, la DLL CRT doit être présent sur le système.  Même si vous liez dynamiquement au CRT, vous pouvez constater que du code peut être lié de manière statique \(par exemple, **DllMainCRTStartup**\).  
  
 Lorsque vous attachez votre image, vous spécifiez explicitement ou implicitement un point d'entrée que le système d'exploitation appelle dans après chargement de l'image.  Pour une DLL, le point d'entrée par défaut est **DllMainCRTStartup**.  Pour un EXE, c'est **WinMainCRTStartup**.  Vous pouvez substituer la valeur par défaut avec l'option de l'éditeur de liens \/ENTRY.  Le CRT fournit une implémentation pour **DllMainCRTStartup**, **WinMainCRTStartup**, et **wWinMainCRTStartup** \(le point d'entrée Unicode pour un EXE\).  Ces Tube\- fournis aux constructeurs d'appel de points d'entrée dans les objets globaux et initialisent d'autres structures de données utilisées par des fonctions CRT.  Ce code de démarrage ajoute à propos de 25K à votre image s'il est lié de manière statique.  S'il est lié dynamiquement, la majeure partie du code est dans la DLL, votre taille de l'image reste petite.  
  
 Pour plus d'informations, consultez la rubrique [\/ENTRY \(Symbole de point d'entrée\)](../build/reference/entry-entry-point-symbol.md)d'éditeur de liens.  
  
## Options d'optimisation  
 À l'aide de l'option de l'éditeur de liens \/OPT : NOWIN98 peut davantage réduire un contrôle par défaut ATL par 10K, aux dépens du temps de chargement augmenté sur les systèmes Windows 98.  Pour plus d'informations sur la liaison des options, consultez [\/OPT \(Optimisations\)](../build/reference/opt-optimizations.md).  
  
## Voir aussi  
 [Programmation avec ATL et le code C Run\-Time](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Comportement de la bibliothèque runtime](../build/run-time-library-behavior.md)