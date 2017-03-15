---
title: "Prise en charge des biblioth&#232;ques de liens dynamiques | Microsoft Docs"
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
  - "DLL (C++), MFC"
  - "DLL MFC (C++), DLL normales"
  - "NAFXDW.LIB"
  - "NAFXDWD.LIB"
  - "DLL normales (C++), projet cible en tant que DLL"
  - "USRDLL, prise en charge DLL"
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Prise en charge des biblioth&#232;ques de liens dynamiques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les bibliothèques de NAFXCW.lib et de NAFXCWD.lib \(répertoriées dans le tableau de conventions d'affectation de noms de la bibliothèque de STATIC\- Link dans [Conventions d'affectation de noms de bibliothèques](../mfc/library-naming-conventions.md)\) créent votre projet en tant que bibliothèque de liens dynamiques, appelée un « DLL normal » \(auparavant appelée un « USRDLL »\) qui peut être utilisée avec les applications non construites avec la bibliothèque de classes.  Cette prise en charge de la DLL n'est pas identique à MFCx0.DLL et MFCx0D.DLL \(appelé AFXDLL\), qui contiennent la bibliothèque de classes entière dans une DLL.  Pour plus d'informations, consultez [DLLs](../build/dlls-in-visual-cpp.md).  Pour une table de noms DLL, consultez [DLL : Conventions d'affectation des noms](../build/naming-conventions-for-mfc-dlls.md).  
  
## Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)