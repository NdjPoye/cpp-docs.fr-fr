---
title: "D&#233;termination de la m&#233;thode d&#39;exportation &#224; utiliser | Microsoft Docs"
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
  - "__declspec(dllexport) (mot clé C++)"
  - "fichiers def (C++), exporter à partir de DLL"
  - "exporter des DLL (C++), comparaison de méthodes"
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;termination de la m&#233;thode d&#39;exportation &#224; utiliser
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez exporter des fonctions dans les deux fichiers à la fois \- un fichier .def ou un mot clé `__declspec(dllexport)`.  Pour vous aider à déterminer quelles méthodes seront élevées pour la DLL, considérez ces questions :  
  
-   Organisez\-vous pour exporter des fonctions ultérieurement ?  
  
-   Est\-ce\-que la DLL est uniquement utilisée par les applications que vous pouvez reconstruire, ou il est utilisé par les applications que vous ne pouvez pas REBUILD\- pour l'exemple, les applications créées par des concepteurs tiers ?  
  
## Avantages et inconvénients de l'utilisation de fichiers .DEF  
 L'exportation de fonctions dans un fichier .def permet de déterminer les ordinaux d'exportation.  Lorsque vous ajoutez une fonction exportée supplémentaire à la DLL, vous pouvez leur assigner une valeur ordinale supérieure \(supérieures à toute autre fonction exportée\).  En ce cas, les applications qui utilisent la liaison implicite n'ont pas besoin d'une réédition de leurs liens avec la nouvelle bibliothèque d'importation contenant les nouvelles fonctions.  Il est très pratique si vous concevez une DLL destinée à de nombreuses applications car vous pouvez ajouter de nouvelles fonctionnalités et également à vérifier qu'elle continue à fonctionner correctement avec les applications qui reposent déjà sur celle\-ci.  Par exemple, les DLL MFC sont générés à l'aide de les fichiers de .def.  
  
 Un autre avantage de l'utilisation d'un fichier .def est que vous pouvez utiliser l'attribut `NONAME` pour exporter une fonction.  Cela met uniquement l'ordinal dans la table d'exportation dans la DLL.  Pour les DLL comportant un grand nombre de fonctions exportées, l'utilisation de l'attribut `NONAME` peut réduire la taille du fichier DLL.  Pour plus d'informations sur la façon d'écrire une instruction de définition de module, consultez [Règles s'appliquant aux instructions de définition de module](../build/reference/rules-for-module-definition-statements.md).  Pour plus d'informations sur l'exportation ordinale, consultez [Exportation de fonctions à partir d'une DLL par ordinal plutôt que par nom](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 Le principal inconvénient lié à l'utilisation d'un fichier .def est que si vous exportez des fonctions dans un fichier C\+\+, vous devez alors soit placer les noms décorés dans le fichier .def soit définir les fonctions exportées à l'aide d'une liaison C standard en utilisant extern "C" afin d'éviter la décoration des noms effectuée par le compilateur Visual C\+\+.  
  
 Si vous placez les noms décorés dans le fichier .def, vous pouvez les obtenir à l'aide de l'outil [DUMPBIN](../build/reference/dumpbin-reference.md) ou en utilisant l'option [\/MAP](../build/reference/map-generate-mapfile.md) de l'éditeur de liens.  Les noms décorés produits par le compilateur sont compilateur\- à la colonne ; par conséquent, si vous mettez des noms décorés produits par le compilateur dans un fichier .def de, les applications qui lient à la DLL doivent également être créées en utilisant la même version du compilateur afin que les noms décorés dans l'application appelante correspondent aux noms exportés dans le fichier de .def de la DLL.  
  
## Avantages et inconvénients de l'utilisation de \_\_declspec\(dllexport\)  
 L'utilisation de `__declspec(dllexport)` est pratique dans la mesure où vous n'avez pas à vous préoccuper de la gestion d'un fichier .def et de l'obtention des noms décorés des fonctions exportées.  Toutefois, l'utilité de cette façon d'exportation est limité par le nombre d'applications liées que vous êtes prêt à reconstruire.  Si vous régénérez la DLL avec de nouvelles exportations, vous devez également régénérer l'application, car les noms décorés des fonctions C\+\+ exportées peuvent changer si vous effectuez une recompilation avec une version différente du compilateur.  
  
### Que voulez\-vous faire ?  
  
-   [Exporter à partir d'une DLL à l'aide de fichiers .DEF](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exporter à partir d'une DLL à l'aide de \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exporter et importer à l'aide de AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exporter des fonctions C\+\+ à utiliser dans des exécutables en langage C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exporter des fonctions C à utiliser dans des exécutables en langage C ou C\+\+](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Importer dans une application à l'aide de \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialiser une DLL](../build/initializing-a-dll.md)  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Importation et exportation de fonctions inline](../build/importing-and-exporting-inline-functions.md)  
  
-   [Importations mutuelles](../build/mutual-imports.md)  
  
-   [Noms décorés](../build/reference/decorated-names.md)  
  
## Voir aussi  
 [Exportation à partir d'une DLL](../build/exporting-from-a-dll.md)