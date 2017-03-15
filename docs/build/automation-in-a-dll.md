---
title: "Automation dans une DLL | Microsoft Docs"
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
  - "Automation (C++), DLL"
  - "DLL (C++), Automation"
ms.assetid: 2728ecd1-14e2-4ae0-a946-e749e11dbb74
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Automation dans une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous choisissez l'option Automation dans l'Assistant DLL MFC, vous obtenez ce qui suit :  
  
-   Un fichier .ODL \(Object Description Language\) de démarrage  
  
-   Une directive Include dans le fichier STDAFX.h pour Afxole.h  
  
-   Une implémentation de la fonction `DllGetClassObject`, qui appelle la fonction **AfxDllGetClassObject**  
  
-   Une implémentation de la fonction `DllCanUnloadNow`, qui appelle la fonction **AfxDllCanUnloadNow**  
  
-   Une implémentation de la fonction `DllRegisterServer`, qui appelle la fonction [COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Serveurs Automation](../mfc/automation-servers.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)