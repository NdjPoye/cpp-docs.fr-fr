---
title: "dllexport, dllimport | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "dllimport_cpp"
  - "dllexport_cpp"
  - "dllexport"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), dllexport"
  - "__declspec (mot clé) (C++), dllimport"
  - "dllexport __declspec (mot clé)"
  - "dllimport __declspec (mot clé)"
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# dllexport, dllimport
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les attributs de classe de stockage `dllexport` et **dllimport** sont des extensions spécifiques à Microsoft pour les langages C et C\+\+.  Vous pouvez les utiliser pour exporter et importer des fonctions, des données et des objets vers ou depuis une DLL.  
  
## Syntaxe  
  
```  
  
        __declspec( dllimport ) declarator  
__declspec( dllexport ) declarator  
```  
  
## Notes  
 Ces attributs définissent explicitement l'interface de la DLL à son client, qui peut être un fichier exécutable ou une autre DLL.  La déclaration de fonctions comme `dllexport` élimine le besoin d'avoir un fichier de définition de module \(.def\), au moins en ce qui concerne la spécification des fonctions exportées.  L'attribut `dllexport` remplace le mot clé `__export`.  
  
 Si une classe est marquée declspec\(dllexport\), les spécialisations des modèles de classe dans la hiérarchie de classes sont implicitement marquées comme declspec\(dllexport\).  Cela signifie que les modèles de classe sont instanciés explicitement et que les membres de la classe doivent être définis.  
  
 `dllexport` d'une fonction expose la fonction avec son nom décoré.  Pour les fonctions C\+\+, cela inclut l'altération des noms.  Pour les fonctions C ou les fonctions déclarées comme `extern "C"`, cela inclut la décoration propre à la plateforme basée sur la convention d'appel.  Pour plus d'informations sur la décoration de nom dans le code C\/C\+\+, consultez [Noms décorés](../build/reference/decorated-names.md).  Aucune décoration de nom n'est appliquée aux fonctions C exportées ni aux fonctions `extern "C"` C\+\+ à l'aide de la convention d'appel `__cdecl`.  
  
 Pour exporter un nom non décoré, vous pouvez établir un lien à l'aide d'un fichier de définition de module \(.def\) qui définit le nom non décoré dans une section EXPORTS.  Pour plus d'informations, consultez [EXPORTS](../build/reference/exports.md).  Une autre façon d'exporter un nom non décoré consiste à utiliser une directive `#pragma comment(linker, "/export:``alias``=``decorated_name``")` dans le code source.  
  
 Lorsque vous déclarez `dllexport` ou **dllimport**, vous devez utiliser la [syntaxe d'attribut étendu](../cpp/declspec.md) et le mot clé `__declspec`.  
  
## Exemple  
  
```cpp  
// Example of the dllimport and dllexport class attributes  
__declspec( dllimport ) int i;  
__declspec( dllexport ) void func();  
```  
  
 Pour rendre votre code plus lisible, vous pouvez aussi utiliser des définitions de macros :  
  
```cpp  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllImport int j;  
DllExport int n;  
```  
  
 Pour plus d'informations, voir :  
  
-   [Définitions et déclarations](../cpp/definitions-and-declarations-cpp.md)  
  
-   [Définition de fonctions C\+\+ incorporées avec dllexport et dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)  
  
-   [Règles générales et limitations](../cpp/general-rules-and-limitations.md)  
  
-   [Utilisation de dllimport et dllexport dans les classes C\+\+](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)