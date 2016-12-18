---
title: "Avantages de la portabilit&#233; d&#39;un jeu de caract&#232;res | Microsoft Docs"
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
  - "jeux de caractères (C++), avantages"
  - "portabilité (C++), jeux de caractères"
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
caps.latest.revision: 8
caps.handback.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Avantages de la portabilit&#233; d&#39;un jeu de caract&#232;res
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il est préférable d'utiliser les fonctionnalités de portabilité runtime MFC et C même si vous ne comptez pas internationaliser votre application pour le moment :  
  
-   Le codage portable rend votre base de code flexible.  Ultérieurement, vous pouvez le convertir facilement en Unicode ou en MBCS.  
  
-   L'utilisation de Unicode rend vos applications Windows 2000 plus efficaces.  Dans la mesure où Windows 2000 utilise Unicode, les chaînes non\-Unicode échangées avec le système d'exploitation doivent être traduites, ce qui peut provoquer du temps de gestion mémoire.  
  
-   L'utilisation de MBCS vous permet de prendre en charge les marchés internationaux sur des plateformes Win32 autre que Windows 2000, par exemple Windows 95 ou Windows 98.  
  
## Voir aussi  
 [Unicode et MBCS](../text/unicode-and-mbcs.md)   
 [Prise en charge pour Unicode](../text/support-for-unicode.md)