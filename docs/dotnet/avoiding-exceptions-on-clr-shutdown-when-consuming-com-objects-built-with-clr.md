---
title: "&#201;viter des exceptions &#224; l&#39;arr&#234;t du CLR lors de l&#39;utilisation d&#39;objets COM g&#233;n&#233;r&#233;s avec&#160;/clr | Microsoft Docs"
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
  - "/clr (option du compilateur C++), exceptions d'arrêt CLR"
  - "/clr (option du compilateur C++), objets COM"
  - "exceptions d'arrêt CLR (C++)"
  - "Interop (C++), exceptions d'arrêt CLR"
  - "interopérabilité (C++), exceptions d'arrêt CLR"
  - "assemblys mixtes (C++), exceptions d'arrêt CLR"
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# &#201;viter des exceptions &#224; l&#39;arr&#234;t du CLR lors de l&#39;utilisation d&#39;objets COM g&#233;n&#233;r&#233;s avec&#160;/clr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fois que le Common Language Runtime \(CLR\) entre en mode d'arrêt, les fonctions natives ont un accès limité aux services CLR.  Lorsqu'on tente d'appeler la version release sur un objet COM compilé avec **\/clr**, le CLR passe en code natif, puis revient en code managé pour répondre à l'appel IUnknown::Release \(défini en code managé\).  Le CLR empêche le rappel en code managé puisqu'il se trouve en mode d'arrêt.  
  
 Pour résoudre le problème, veillez à ce que les destructeurs appelés depuis des méthodes release ne contiennent que du code natif.  
  
## Voir aussi  
 [Assemblys mixtes \(natif et managé\)](../dotnet/mixed-native-and-managed-assemblies.md)