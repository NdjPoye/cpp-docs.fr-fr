---
title: "Conventions d&#39;affectation de noms pour les DLL MFC | Microsoft Docs"
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
  - "DLL (C++), noms de bibliothèques"
  - "DLL (C++), conventions d'affectation de noms"
  - "bibliothèques (C++), noms des DLL MFC"
  - "DLL MFC (C++), conventions d'affectation de noms"
  - "bibliothèques MFC (C++), conventions d'affectation de noms"
  - "conventions d'affectation de noms (C++), DLL MFC"
  - "versions DLL partagées (C++)"
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Conventions d&#39;affectation de noms pour les DLL MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les DLL et les bibliothèques incluses dans les MFC obéissent aux règles d'une convention d'attribution de noms structurée.  Cela vous permet de déterminer plus facilement la DLL ou la bibliothèque que vous devez utiliser dans chaque cas.  
  
 Les bibliothèques d'importation requises pour la génération des applications ou des DLL d'extension qui utilisent ces DLL ont le même nom de base que la DLL sauf qu'elles portent une extension de nom de fichier .lib.  
  
### Convention d'attribution de noms aux DLL partagées  
  
|DLL|Description|  
|---------|-----------------|  
|MFCx0.DLL|DLL MFC, version Release ANSI|  
|MFCx0U.DLL|DLL MFC, version Release Unicode|  
|MFCx0D.DLL|DLL MFC, version Debug ANSI|  
|MFCx0UD.DLL|DLL MFC, version Debug Unicode|  
  
 Si vous établissez une liaison de manière dynamique avec la version DLL partagée de MFC, que ce soit à partir d'une application ou d'une DLL d'extension, vous devez inclure MFCx0.DLL avec votre produit.  Si vous avez besoin d'une prise en charge Unicode dans votre application, incorporez plutôt MFCx0U.DLL.  
  
 Si vous liez de manière statique votre DLL aux MFC, vous devez la lier à l'aide de l'une des bibliothèques MFC statiques.  Ces versions sont nommées d'après la convention \[N&#124;U\]AFXCW\[D\].LIB.  Pour plus d'informations, consultez le tableau « Conventions d'affectation de noms aux bibliothèques de liaison statique » dans [Conventions d'affectation de noms aux bibliothèques](../mfc/library-naming-conventions.md) \(MFC\).  
  
 Pour obtenir la liste des DLL Visual C\+\+ qui peuvent être distribuées avec vos applications, consultez Redist.txt dans votre installation Visual Studio.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Convention d'affectation de noms aux bibliothèques](../mfc/library-naming-conventions.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)