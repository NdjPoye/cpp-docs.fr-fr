---
title: "#using, directive (C++) | Microsoft Docs"
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
  - "friend_as_cpp"
  - "#using"
  - "friend_as"
  - "#using_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#using (directive)"
  - "LIBPATH (variable d'environnement)"
  - "préprocesseur, directives"
  - "directive using (#using)"
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #using, directive (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Importe des métadonnées dans un programme compilé avec [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Syntaxe  
  
```  
#using file [as_friend]  
```  
  
#### Paramètres  
 `file`  
 Un MSIL .dll, .exe, .netmodule, ou .obj.  Par exemple :  
  
 `#using <MyComponent.dll>`  
  
 as\_friend  
 Spécifie que tous les types de `file` sont accessibles.  Pour plus d'informations, consultez [Assemblys friend \(C\+\+\)](../dotnet/friend-assemblies-cpp.md).  
  
## Notes  
 `file` peut être un fichier Microsoft intermediate language \(MSIL\) que vous importez pour ses données managées et ses constructions gérées.  Si un fichier .dll contient un manifeste d'assembly, alors tous les .dll référencés dans le manifeste sont importés et l'assembly que vous générez listera *file* dans les métadonnées comme référence d'assembly.  
  
 Si `file` ne contient pas d'assembly \(si `file` est un module\) et si vous n'envisagez pas d'utiliser des informations de type du module de l'application \(d'assembly\) actuelle , vous avez la possibilité de simplement indiquer que le module est une partie de l'assembly ; utilisez [\/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  Les types dans le module sont ensuite disponibles pour toute application qui a référencé l'assembly.  
  
 Au lieu d'utiliser `#using` il est possible d'utiliser l'option du compilateur [\/FU](../build/reference/fu-name-forced-hash-using-file.md).  
  
 Des assemblys .exe passés à `#using` doivent être compilés avec **\/clr:safe** ou **\/clr:pure**, ou avec l'un des autres compilateurs Visual Studio \(Visual Basic ou Visual C\#, par exemple\).  Si vous essayez d'importer des métadonnées d'un assembly .exe compilé avec **\/clr**, cela provoquera une exception de chargement du fichier.  
  
> [!NOTE]
>  Un composant qui est référencé avec `#using` peut être exécuté avec une version différente du fichier importé au moment de la compilation, causant une application cliente à donner des résultats inattendus.  
  
 Pour qu'un compilateur reconnaisse un type dans un assembly \(pas un module\), il doit résoudre le type. Pour ce faire, vous pouvez par exemple définir une instance du type.  Le compilateur peut résoudre les noms de types d'un assembly de plusieurs autres façons : par exemple, lorsqu'un type est hérité d'un autre type d'un assembly, le nom du type est alors connu du compilateur.  
  
 Quand vous importez des métadonnées générées depuis du code source ayant utilisé [\_\_declspec \(thread\)](../cpp/thread.md), la sémantique de threads n'est pas persistante dans les métadonnées.  Par exemple, une variable déclarée avec **\_\_declspec\(thread\)**, compilée dans un programme qui est fait pour le Common Langage Runtime de .NET Framework, puis importée via `#using`, n'a plus la sémantique **\_\_declspec\(thread\)** sur la variable.  
  
 Tous les types importés \(managé et natif\) dans un fichier référencé par `#using` sont disponibles, mais le compilateur traite les types natifs comme des déclarations et non pas comme des définitions.  
  
 mscorlib.dll est automatiquement référencé en compilant avec **\/clr**.  
  
 La variable d'environnement LIBPATH spécifie les répertoires qui seront fouillés lorsque le compilateur tente de résoudre des noms de fichiers passés à `#using`.  
  
 Le compilateur recherchera les références sur le chemin suivant :  
  
-   Un chemin d'accès spécifié dans l'instruction `#using`.  
  
-   Le répertoire actif.  
  
-   Le répertoire système .NET Framework.  
  
-   Répertoires ajoutés avec l'option [\/AI](../build/reference/ai-specify-metadata-directories.md) du compilateur.  
  
-   Répertoires sur la variable d'environnement LIBPATH.  
  
## Exemple  
 Si vous générez un assembly \(C\) et référencez un assembly \(B\) qui lui\-même référence un autre assembly \(A\), vous n'avez pas a faire référence à l'assembly A explicitement à moins que vous n'utilisiez un des types de A dans C.  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## Exemple  
  
```  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};  
  
```  
  
## Exemple  
 Dans l'exemple suivant, il n'y a aucune erreur du compilateur pour non\-référencement d'using\_assembly\_A.dll car le programme n'utilise aucun des types définis dans using\_assembly\_A.cpp.  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)