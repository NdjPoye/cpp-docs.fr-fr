---
title: "Benefits and Tradeoffs of the Method Used to Link to the CRT | Microsoft Docs"
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
  - "_ATL_MIN_CRT (macro)"
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Benefits and Tradeoffs of the Method Used to Link to the CRT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Votre projet peut établir une liaison avec le CRT dynamique ou statique.  Le tableau ci\-dessous des contours les avantages et les compromis impliqué en choisissant qui méthode à utiliser.  
  
|Méthode|Avantage|Compromis|  
|-------------|--------------|---------------|  
|Statiquement liant au CRT<br /><br /> \(**Runtime Library** défini à **Single\-threaded**\)|La DLL CRT n'est pas obligatoire du système où l'image s'exécutera.|Sur 25K de code de démarrage est ajouté à votre image, l'augmentation considérablement la taille.|  
|La liaison dynamique au CRT<br /><br /> \(**Runtime Library** défini à **Multi\-threaded**\)|Votre image ne requiert pas le code de démarrage CRT, elle est plus petite.|La DLL CRT doit être sur le système exécutant l'image.|  
  
 La rubrique [Lier au CRT dans votre projet ATL](../atl/linking-to-the-crt-in-your-atl-project.md) explique comment sélectionner la façon dont le lien au CRT.  
  
## Voir aussi  
 [Programmation avec ATL et le code C Run\-Time](../atl/programming-with-atl-and-c-run-time-code.md)   
 [Comportement de la bibliothèque runtime](../build/run-time-library-behavior.md)   
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)