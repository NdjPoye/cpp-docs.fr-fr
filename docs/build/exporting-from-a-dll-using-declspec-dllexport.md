---
title: "Exportation &#224; partir d&#39;une DLL &#224; l&#39;aide de&#160;__declspec(dllexport) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllexport"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllexport) (mot clé C++)"
  - "export (directive) (C++)"
  - "exporter des DLL (C++), __declspec(dllexport) (mot clé)"
  - "noms (C++), exportations DLL par"
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Exportation &#224; partir d&#39;une DLL &#224; l&#39;aide de&#160;__declspec(dllexport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft a introduit **\_\_export** dans la version 16 bits du compilateur de Visual C\+\+ afin de permettre à ce compilateur de générer automatiquement les noms des exportations et de les placer dans un fichier .lib.  Ce fichier .lib peut ensuite être utilisé comme un fichier .lib statique pour établir une liaison avec une DLL.  
  
 Dans les versions les plus récentes du compilateur, vous pouvez exporter les données, les fonctions, les classes ou les fonctions membres d'une classe à partir d'une DLL à l'aide du mot clé **\_\_declspec\(dllexport\)**.  **\_\_declspec\(dllexport\)** ajoute la directive d'exportation au fichier objet, vous n'avez pas besoin d'utiliser un fichier .def.  
  
 Ce côté pratique est surtout visible lorsque vous essayez d'exporter des noms décorés de fonctions C\+\+.  Comme il n'existe pas de spécification standard pour la décoration des noms, le nom d'une fonction exportée peut changer d'une version de compilateur à l'autre.  Si vous utilisez **\_\_declspec\(dllexport\)**, la recompilation de la DLL et des fichiers .exe dépendants est nécessaire uniquement pour tenir compte d'éventuelles modifications intervenues dans la convention d'attribution de noms.  
  
 De nombreuses directives d'exportation, telles que les ordinaux, NONAME et PRIVATE, ne peuvent être insérées que dans un fichier .def, et il n'existe aucun moyen de spécifier ces attributs sans un fichier .def.  Cependant, l'utilisation de **\_\_declspec\(dllexport\)** en plus de celle d'un fichier .def ne provoque pas d'erreur de build.  
  
 Pour exporter des fonctions, le mot clé **\_\_declspec\(dllexport\)** doit apparaître à gauche du mot clé de la convention d'appel, si un mot clé est spécifié.  Par exemple :  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Pour exporter toutes les données membres publiques et les fonctions membres d'une classe, vous devez faire figurer le mot clé à gauche du nom de la classe, comme suit :  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)` ne peut pas être appliqué à une fonction avec la convention d'appel `__clrcall`.  
  
 Lorsque vous générez la DLL, vous créez généralement un fichier d'en\-tête contenant les prototypes et\/ou les classes des fonctions que vous exportez, puis ajoutez **\_\_declspec\(dllexport\)** aux déclarations du fichier d'en\-tête.  Pour rendre le code plus lisible, définissez une macro pour **\_\_declspec\(dllexport\)** puis utilisez cette macro avec chaque symbole exporté :  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **\_\_declspec\(dllexport\)** stocke des noms de fonctions dans la table d'exportations de la DLL.  Si vous souhaitez optimiser la taille de la table, consultez [Exportation de fonctions à partir d'une DLL par ordinal plutôt que par nom](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  Lorsque vous convertissez le code source de la DLL de Win16 en Win32, remplacez chaque instance de **\_\_export** par **\_\_declspec\(dllexport\)**.  
  
 Comme référence, parcourez le fichier d'en\-tête Winbase.h Win32.  Il contient des exemples d'utilisation de **\_\_declspec\(dllimport\)**.  
  
## Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .def](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Déterminer la méthode d'exportation à utiliser](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Mot clé \_\_declspec](../cpp/declspec.md)  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)