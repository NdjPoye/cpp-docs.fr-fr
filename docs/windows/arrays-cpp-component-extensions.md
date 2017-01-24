---
title: "Arrays (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "cli::array"
  - "details::array"
  - "lang::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array keyword [C++]"
  - "declaring arrays, about declaring arrays"
  - "arrays [C++], multidimensional"
  - "multidimensional arrays"
  - "arrays [C++]"
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le type `Platform::Array<T>` dans [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)], ou le mot clé `array` dans [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)], déclare un tableau d'un type et une valeur initiale spécifiés.  
  
## Toutes les plateformes  
 La table doit être déclarée à l'aide du modificateur de handle\-à\-OBJECT \(^\) après le signe supérieur à \(\>\) dans la déclaration.  
  
 Le nombre d'éléments du tableau ne fait pas partie du type.  Une variable table peut faire référence à des tableaux de différentes tailles.  
  
 Contrairement à C\+\+ standard, l'indiçage n'est pas un synonyme pour des opérations arithmétiques sur des pointeurs et n'est pas commutatif.  
  
 Pour plus d'informations sur les tableaux, consultez:  
  
-   [Covariance de tableau](../misc/array-covariance.md)  
  
-   [Comment : utiliser des tableaux dans C\+\+\/CLI](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
  
-   [Comment : créer des tableaux multidimensionnels](../misc/how-to-create-multidimension-arrays.md)  
  
-   [Comment : créer des tableaux de tableaux managés \(tableaux en escalier\)](../misc/how-to-create-arrays-of-managed-arrays-jagged-arrays.md)  
  
-   [Comment : faire des Typedefs pour des tableaux gérés](../misc/how-to-make-typedefs-for-managed-arrays.md)  
  
-   [Comment : utiliser des tableaux managés en tant que paramètres de type de modèle](../misc/how-to-use-managed-arrays-as-template-type-parameters.md)  
  
-   [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
-   [Comment : trier des tableaux](../misc/how-to-sort-arrays.md)  
  
-   [Comment : trier des tableaux à l'aide de critères personnalisés](../misc/how-to-sort-arrays-using-custom-criteria.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Les tables sont des membres de l'espace de noms `Platform`.  Les tables peuvent être unidimensionnels.  
  
 **Syntaxe**  
  
 Le premier exemple de syntaxe utilise le mot clé d'agrégation `ref new` pour allouer une table.  Le deuxième exemple déclare un tableau local.  
  
```  
  
        [qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = ref new [Platform::]Array< initialization-type > [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[facultatif\]  
 Une ou plusieurs de ces spécificateurs de classe de stockage : [mutable](../cpp/mutable-data-members-cpp.md), [volatiles](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statiques](../misc/static-cpp.md).  
  
 `array-type`  
 Le type des variables du tableau.  Les types valides sont les classes [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] les types fondamentaux, les classes et les structs de référence, les classes et les structs de valeurs, et des pointeurs natifs \(`type``*`\).  
  
 `rank` \[facultatif\]  
 Nombre de dimensions du tableau.  Doit être 1.  
  
 `identifier`  
 Nom de la variable de la table.  
  
 `initialization-type`  
 Le type des valeurs qui initialisent le tableau.  En général, `array-type` et `initialization-type` sont du même type.  Toutefois, les types peuvent être différents s'il existe une conversion `initialization-type` à `array-type`par exemple, si `initialization-type` est dérivé de `array-type`.  
  
 `initialization-list` \[facultatif\]  
 Une liste séparée par des virgules de valeurs dans des accolades qui initialisent les éléments du tableau.  Par exemple, si `rank-size-list` ont été `(3)`, qui déclare un tableau de 3 éléments, `initialization list` peut être `{1,2,3}`.  
  
 **Remarques**  
  
 Vous pouvez détecter au moment de la compilation si un type est un tableau référence\-compté avec `__is_ref_array(``type``)`.  Pour plus d'informations, consultez [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
### Exemples  
 L'exemple suivant crée un tableau contenant 100 éléments.  
  
```  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntaxe**  
  
 Le premier exemple de syntaxe utilise le mot clé `gcnew` pour allouer une table.  Le deuxième exemple déclare un tableau local.  
  
```  
  
        [qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = gcnew [cli::]array< initialization-type [,rank] >(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[facultatif\]  
 Une ou plusieurs de ces spécificateurs de classe de stockage : [mutable](../cpp/mutable-data-members-cpp.md), [volatiles](../cpp/volatile-cpp.md), [const](../cpp/const-cpp.md), [extern](../cpp/using-extern-to-specify-linkage.md), [statiques](../misc/static-cpp.md).  
  
 `array-type`  
 Le type des variables du tableau.  Les types valides sont les classes [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et les types fondamentaux, les classes et les structs de référence, les classes et les structs de valeur, les pointeurs natifs \(`type``*`\), la COSSE native \(anciennes données ordinaires\).  
  
 `rank` \[facultatif\]  
 Nombre de dimensions du tableau.  La valeur par défaut est 1 ; le maximum est 32.  Chaque dimension du tableau est elle\-même un tableau.  
  
 `identifier`  
 Nom de la variable de la table.  
  
 `initialization-type`  
 Le type des valeurs qui initialisent le tableau.  En général, `array-type` et `initialization-type` sont du même type.  Toutefois, les types peuvent être différents s'il existe une conversion `initialization-type` à `array-type`par exemple, si `initialization-type` est dérivé de `array-type`.  
  
 `rank-size-list`  
 Une liste séparée par des virgules de la taille de chaque dimension dans le tableau.  Sinon, si le paramètre `initialization-list` est spécifié, le compilateur peut déduire la taille de chaque dimension et `rank-size-list` peut être omis.  Pour plus d'informations, consultez [Comment : créer des tableaux multidimensionnels](../misc/how-to-create-multidimension-arrays.md).  
  
 `initialization-list` \[facultatif\]  
 Une liste séparée par des virgules de valeurs dans des accolades qui initialisent les éléments du tableau.  Ou une liste séparée par des virgules d'éléments imbriqués *initialization\-list* qui initialisent les éléments d'un tableau multidimensionnel.  
  
 Par exemple, si `rank-size-list` ont été `(3)`, qui déclare un tableau de 3 éléments, `initialization list` peut être `{1,2,3}`.  Si `rank-size-list` ont été `(3,2,4)`, qui déclare un tableau en trois dimensions à 3 éléments dans la première dimension, 2 éléments dans la seconde, et 4 éléments dans le troisième, `initialization-list` peuvent être `{{1,2,3},{0,0},{-5,10,-21,99}}`.\)  
  
 **Remarques**  
  
 `array` est dans l'espace de noms [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Comme C\+\+ standard, les index d'une table sont de base zéro, et un tableau est indicé à l'aide de crochets \(\[\]\).  Contrairement à C\+\+ standard, les index d'une table MDX sont spécifiées dans une liste d'index pour chaque dimension au lieu d'un ensemble d'opérateurs de crochets \(\[\]\) pour chaque dimension.  Par exemple, *identifier*\[*index1*, *index2*\] au lieu de *identifier*\[*index1*\]\[ *index2*\].  
  
 Les tableaux managés héritent de `System::Array`.  N'importe quelle méthode ou propriété `System::Array` peut être appliqué directement à la variable de table.  
  
 Lorsque vous allouez un tableau dont le type d'élément est pointeur\- vers une classe managée, les éléments sont 0 initialisé.  
  
 Lorsque vous allouez un tableau dont le type d'élément est un type de valeur `V`, le constructeur par défaut pour `V` est appliqué à chaque élément du tableau.  Pour plus d'informations, consultez [Équivalents .NET Framework des types natifs C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md).  
  
 Au moment de la compilation, vous pouvez détecter si un type est une table common langage runtime \(CLR\) avec `__is_ref_array(``type``)`.  Pour plus d'informations, consultez [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 L'exemple suivant crée un tableau contenant 100 éléments, et un tableau en trois dimensions contenant 3 éléments dans la première dimension, 5 éléments de seconde, et 6 éléments dans le troisième.  
  
```  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)