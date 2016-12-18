---
title: "Exportation &#224; partir d&#39;une DLL &#224; l&#39;aide de fichiers DEF | Microsoft Docs"
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
  - "fichiers .def (C++), exporter à partir de DLL"
  - "fichiers def (C++), exporter à partir de DLL"
  - "exporter des DLL (C++), fichiers DEF"
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation &#224; partir d&#39;une DLL &#224; l&#39;aide de fichiers DEF
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un fichier de définition de module \(.def\) est un fichier texte contenant une ou plusieurs instructions du module décrivant divers attributs d'une DLL.  Si vous n'utilisez pas le mot clé **\_\_declspec\(dllexport\)** pour exporter des fonctions de la DLL, la DLL exige un fichier .def.  
  
 Un fichier .def minimal doit contenir les instructions de définition de module suivantes :  
  
-   La première instruction dans le fichier doit être l'instruction LIBRARY.  Cette instruction identifie le fichier .def comme appartenant à une DLL.  L'instruction LIBRARY est suivie du nom de la DLL.  L'éditeur de liens place ce nom dans la bibliothèque d'importation de la DLL.  
  
-   L'instruction EXPORTS dresse la liste des noms et, éventuellement, des valeurs ordinales des fonctions exportées par la DLL.  Vous assignez à la fonction une valeur ordinale en faisant suivre le nom de la fonction d'un signe \(@\) et d'un nombre.  Lorsque vous spécifiez des valeurs ordinales, celles\-ci doivent se situer dans la plage 1 à N, où N est le nombre de fonctions exportées par la DLL.  Si vous souhaitez exporter des fonctions par ordinal, consultez [Exportation de fonctions à partir d'une DLL par ordinal plutôt que par nom](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) ainsi que cette rubrique.  
  
 Par exemple, une DLL qui contient le code d'implémentation d'un arbre de recherche binaire peut ressembler à ce qui suit :  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 Si vous utilisez l'[Assistant DLL MFC](../mfc/reference/mfc-dll-wizard.md) pour créer une DLL MFC, l'Assistant crée un squelette de fichier .def et l'ajoute automatiquement à votre projet.  Ajoutez les noms des fonctions à exporter dans ce fichier.  Pour les DLL non\-MFC, vous devez créer vous\-même le fichier .def et l'ajouter à votre projet.  
  
 Si vous exportez des fonctions dans un fichier C\+\+, vous devez alors soit placer les noms décorés dans le fichier .def soit définir les fonctions exportées à l'aide d'une liaison C standard en utilisant extern "C".  Si vous devez placer les noms décorés dans le fichier .def, vous pouvez les obtenir à l'aide de l'outil [DUMPBIN](../build/reference/dumpbin-reference.md) ou en utilisant l'option [\/MAP](../build/reference/map-generate-mapfile.md) de l'éditeur de liens.  Notez que les noms décorés produits par le compilateur sont spécifiques à celui\-ci.  Si vous placez les noms décorés générés par le compilateur Visual C\+\+ dans un fichier .def, les applications qui sont liées à votre DLL doivent, elles aussi, être générées à l'aide de la même version de Visual C\+\+, afin que les noms décorés dans l'application appelante correspondent aux noms exportés dans le fichier .def de la DLL.  
  
 Si vous générez une [DLL d'extension](../build/extension-dlls-overview.md) et exportez à l'aide d'un fichier .def, placez le code suivant au début et à la fin des fichiers d'en\-tête contenant les classes exportées :  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Ces lignes garantissent que les variables MFC utilisées de manière interne ou ajoutées à vos classes seront exportées \(ou importées\) à partir de la DLL d'extension.  Par exemple, lorsque vous dérivez une classe à l'aide de `DECLARE_DYNAMIC`, la macro se développe de manière à ajouter une variable membre `CRuntimeClass` à votre classe.  Si vous omettez ces quatre lignes, la DLL risque d'être compilée ou liée de manière incorrecte ou de générer une erreur lorsque l'application client établit une liaison avec elle.  
  
 Lors de la génération de la DLL, l'éditeur de liens utilise le fichier .def pour créer un fichier d'exportation \(.exp\) et un fichier de bibliothèque d'importation \(.lib\).  L'éditeur de liens utilise ensuite le fichier d'exportation pour générer le fichier DLL.  Les exécutables liés de manière implicite à la DLL sont liés à la bibliothèque d'importation une fois générés.  
  
 Notez que les MFC eux\-mêmes utilisent des fichiers .def pour exporter des fonctions et des classes à partir de MFCx0.dll.  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Fichiers .def](../build/reference/module-definition-dot-def-files.md)  
  
-   [Règles s'appliquant aux instructions de définition de module](../build/reference/rules-for-module-definition-statements.md)  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)