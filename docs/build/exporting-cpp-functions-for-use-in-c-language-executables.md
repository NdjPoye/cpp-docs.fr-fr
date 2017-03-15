---
title: "Exportation de fonctions&#160;C++ &#224; utiliser dans des ex&#233;cutables en langage&#160;C | Microsoft Docs"
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
  - "exporter des DLL (C++), fonctions C++ dans les exécutables C"
  - "exporter des fonctions (C++), fonctions C++ dans les exécutables C"
  - "fonctions (C++), fonctions C++ dans les exécutables C"
  - "fonctions (C++), exporter"
ms.assetid: 80b9e982-f52d-4312-a891-f73cc69f3c2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation de fonctions&#160;C++ &#224; utiliser dans des ex&#233;cutables en langage&#160;C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si, dans une DLL écrite en C\+\+, vous avez des fonctions auxquelles vous souhaitez accéder à partir d'un module en langage C, vous devez déclarer ces fonctions à l'aide d'une liaison C de préférence à une liaison C\+\+.  Sauf indication contraire, le compilateur C\+\+ utilise la convention d'attribution de noms de types sécurisée du C\+\+ \(appelée également décoration de noms\) et les conventions d'appel du C\+\+, qu'il est parfois difficile d'appeler à partir du C.  
  
 Pour spécifier une liaison C, indiquez **extern** "**C**" dans les déclarations de fonctions.  Par exemple :  
  
```  
extern "C" __declspec( dllexport ) int MyFunc(long parm1);  
```  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
-   [Spécifications de liaison](http://msdn.microsoft.com/fr-fr/d2b0cff1-7798-4c38-9ac8-61c3bfe2bfb9)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)