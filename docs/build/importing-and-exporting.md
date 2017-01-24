---
title: "Importation et exportation | Microsoft Docs"
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
  - "__declspec(dllimport) (mot clé C++)"
  - "DLL (C++), exporter à partir de"
  - "DLL (C++), importer"
  - "exporter des DLL (C++)"
  - "importer des DLL (C++)"
ms.assetid: 7c44c2aa-2117-4cec-9615-a65bfd3f8f7b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Importation et exportation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez importer des symboles publics dans une application ou exporter des fonctions à partir d'une DLL à l'aide de deux méthodes :  
  
-   Utilisation d'un fichier de définition de module \(.def\) lors de la génération de la DLL  
  
-   Utilisation des mots clés **\_\_declspec\(dllimport\)** ou **\_\_declspec\(dllexport\)** dans une définition de fonction dans l'application principale  
  
## Utilisation d'un fichier .def  
 Un fichier de définition de module \(.def\) est un fichier texte contenant une ou plusieurs instructions du module décrivant divers attributs d'une DLL.  Si vous n'utilisez ni **\_\_declspec\(dllimport\)** ni **\_\_declspec\(dllexport\)** pour exporter des fonctions d'une DLL, la DLL exige un fichier .def.  
  
 Vous pouvez utiliser des fichiers .def pour [importer dans une application](../build/importing-using-def-files.md) ou [exporter à partir d'une DLL](../build/exporting-from-a-dll-using-def-files.md).  
  
## Utilisation de \_\_declspec  
 Visual C\+\+ utilise **\_\_declspec\(dllimport\)** et **\_\_declspec\(dllexport\)** pour remplacer le mot clé **\_\_export** utilisé précédemment dans les versions 16 bits de Visual C\+\+.  
  
 Vous n'avez pas besoin d'utiliser **\_\_declspec\(dllimport\)** pour que le code se compile correctement, mais en l'utilisant vous permettez au compilateur de générer un code de meilleure qualité.  Le compilateur est en mesure de générer un code de meilleure qualité, car il peut déterminer si une fonction existe ou non dans une DLL ; il peut donc produire un code qui saute un niveau d'adressage indirect qui serait normalement présent dans un appel de fonction ayant dépassé la limite d'une DLL.  Cependant, vous devez utiliser **\_\_declspec\(dllimport\)** afin d'importer des variables utilisées dans une DLL.  
  
 Avec la section EXPORTS appropriée du fichier .def, **\_\_declspec\(dllexport\)** n'est pas nécessaire.  **\_\_declspec\(dllexport\)** a été ajouté pour mettre en œuvre un moyen pratique d'exportation de fonctions à partir d'un fichier .exe ou .dll sans utiliser un fichier .def.  
  
 Le format d'exécutable portable \(PE, Portable Executable\) Win32 est conçu pour réduire le nombre de pages qu'il faut retoucher pour réparer les importations.  Pour ce faire, il place toutes les adresses d'importation d'un programme dans un emplacement unique appelé Table des adresses d'importation.  Le chargeur peut ainsi modifier une ou deux pages seulement lors de l'accès à ces importations.  
  
## Que voulez\-vous faire ?  
  
-   [Importer dans une application](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Exporter à partir d'une DLL](../build/exporting-from-a-dll.md)  
  
## Voir aussi  
 [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md)