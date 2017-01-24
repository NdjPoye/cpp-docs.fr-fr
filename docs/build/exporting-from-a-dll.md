---
title: "Exportation &#224; partir d&#39;une DLL | Microsoft Docs"
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
  - "exportations de DLL (C++)"
  - "DLL (C++), exporter à partir de"
  - "exporter des DLL (C++)"
  - "exporter des DLL (C++), à propos de l'exportation à partir de DLL"
  - "exporter des fonctions (C++), DLL (exporter à partir de)"
  - "table d'exportations (C++)"
  - "fonctions (C++), exporter"
ms.assetid: a08f86c4-5996-460b-ae54-da2b764045f0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation &#224; partir d&#39;une DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un fichier .DLL a une structure similaire à celle d'un fichier .exe, à une différence importante près : un fichier DLL contient une table d'exportations.  La table d'exportations contient le nom de chaque fonction que la DLL exporte vers d'autres exécutables.  Ces fonctions sont les points d'entrée dans la DLL ; seules les fonctions figurant dans la table d'exportations sont accessibles par d'autres exécutables.  Les autres fonctions de la DLL restent l'exclusivité de la DLL.  La table d'exportations d'une DLL peut être affichée à l'aide de l'outil [DUMPBIN](../build/reference/dumpbin-reference.md) avec l'option \/EXPORTS.  
  
 Vous pouvez exporter des fonctions à partir d'une DLL selon deux méthodes :  
  
-   Créez un fichier de définition de module \(.def\) et utilisez\-le lors de la génération de la DLL.  N'adoptez cette approche que si vous souhaitez [exporter des fonctions à partir de la DLL par ordinal plutôt que par nom](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
-   Utilisez le mot clé **\_\_declspec\(dllexport\)** dans la définition de la fonction.  
  
 Lorsque vous exportez des fonctions par l'une de ces méthodes, veillez à utiliser la convention d'appel [\_\_stdcall](../cpp/stdcall.md).  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Exporter des fonctions à partir d'une DLL par ordinal plutôt que par nom](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Importation dans une application](../build/importing-into-an-application.md)  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
## Voir aussi  
 [Importation et exportation](../build/importing-and-exporting.md)