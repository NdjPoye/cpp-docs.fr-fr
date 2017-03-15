---
title: "Liaison implicite | Microsoft Docs"
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
  - "liaison implicite (C++)"
  - "liaison dynamique au moment du chargement (C++)"
  - "liaison de charge statique (C++)"
ms.assetid: 3ea4c316-4e70-4111-9944-c1b4ad00c605
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Liaison implicite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour une liaison implicite avec une DLL, les exécutables doivent obtenir du fournisseur de la DLL les éléments suivants :  
  
-   Un fichier d'en\-tête \(fichier .h\) contenant les déclarations des fonctions exportées et\/ou des classes C\+\+.  Les classes, fonctions et données doivent toutes posséder `__declspec(dllimport)` ; pour plus d'informations, consultez [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
-   Une bibliothèque d'importation \([fichiers LIB](../build/reference/dot-lib-files-as-linker-input.md)\) à laquelle il faut se lier. \(L'éditeur de liens crée la bibliothèque d'importation lors de la génération de la DLL.\)  
  
-   La DLL effective \(fichier .Dll\).  
  
 Les exécutables qui utilisent la DLL doivent inclure le fichier d'en\-tête contenant les fonctions exportées \(ou les classes C\+\+\) dans chaque fichier source renfermant des appels aux fonctions exportées.  Sur le plan du code, les appels de fonction adressés aux fonctions exportées ressemblent à n'importe quel autre appel de fonction.  
  
 Pour générer le fichier exécutable appelant, vous devez établir une liaison avec la bibliothèque d'importation.  Si vous utilisez un makefile externe, spécifiez le nom du fichier de la bibliothèque d'importation listant d'autres fichiers objet \(.obj\) ou bibliothèques avec lesquels vous établissez une liaison.  
  
 Le système d'exploitation doit pouvoir localiser le fichier .DLL quand il charge l'exécutable appelant.  
  
## Que voulez\-vous faire ?  
  
-   [Lier de manière explicite](../build/linking-explicitly.md)  
  
-   [Déterminer la méthode de liaison à utiliser](../build/determining-which-linking-method-to-use.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de bibliothèques d'importation et de fichiers d'exportation](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Chemin de recherche utilisé par Windows pour retrouver une DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Voir aussi  
 [Liaison d'un exécutable à une DLL](../build/linking-an-executable-to-a-dll.md)