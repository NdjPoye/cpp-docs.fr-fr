---
title: "Importation et exportation de fonctions inline | Microsoft Docs"
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
  - "DLL (C++), exporter à partir de"
  - "DLL (C++), importer"
  - "exporter des fonctions (C++), fonctions inline"
  - "fonctions (C++), exporter"
  - "fonctions (C++), importer"
  - "importer des fonctions (C++)"
  - "importer des fonctions inline (C++)"
  - "fonctions inline (C++), exporter"
  - "fonctions inline (C++), importer"
ms.assetid: 89f488f8-b078-40fe-afd7-80bd7840057b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Importation et exportation de fonctions inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions importées peuvent être définies comme étant inline.  L'effet est à peu près le même que lors de la définition d'une fonction inline standard ; les appels à la fonction sont développés en code incorporé, à l'instar d'une macro.  Cette approche est essentiellement utile en tant que méthode de prise en charge des classes C\+\+ dans une DLL dont certaines fonctions membres peuvent être inline à des fins d'amélioration des performances.  
  
 Une fonction inline importée permet notamment de prendre son adresse en C\+\+.  Le compilateur retourne l'adresse de la copie de la fonction inline résidant dans la DLL.  Une autre fonctionnalité des fonctions inline importées est que, contrairement aux données importées globales, vous pouvez initialiser les données locales statiques de la fonction importée.  
  
> [!CAUTION]
>  Soyez vigilant lorsque vous fournissez des fonctions inline importées, car elles peuvent donner lieu à des conflits de versions.  Une fonction inline est développée en code d'application ; par conséquent, si vous réécrivez la fonction par la suite, celle\-ci n'est mise à jour que si l'application elle\-même est recompilée. \(En principe, les fonctions de la DLL peuvent être mises à jour sans régénération des applications qui les utilisent.\)  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .DEF](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
## Voir aussi  
 [Importation et exportation](../build/importing-and-exporting.md)