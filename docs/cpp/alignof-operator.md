---
title: "__alignof, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__alignof"
  - "alignof"
  - "alignas"
  - "__alignof_cpp"
  - "alignof_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__alignof (mot clé) (C++)"
  - "alignas"
  - "alignement de structures"
  - "alignof"
  - "types (C++), exigences en matière d'alignement"
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# __alignof, op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+11 présente l'opérateur `alignof` qui retourne l'alignement, en octets, du type spécifié.  Pour une portabilité maximale, vous devez utiliser l'opérateur alignof au lieu de l'opérateur \_\_alignof spécifique à Microsoft.  
  
 **Section spécifique à Microsoft**  
  
 Retourne une valeur de type **size\_t** qui est la spécification d'alignement du type.  
  
## Syntaxe  
  
```  
  
        __alignof(   
   type    
)  
```  
  
## Notes  
 Exemple :  
  
|Expression|Valeur|  
|----------------|------------|  
|**\_\_alignof\( char \)**|1|  
|**\_\_alignof \( short \)**|2|  
|**\_\_alignof\( int \)**|4|  
|**\_\_alignof \( \_\_int64 \)**|8|  
|**\_\_alignof \( float \)**|4|  
|**\_\_alignof \( double \)**|8|  
|**\_\_alignof\( char\* \)**|4|  
  
 La valeur de `__alignof` est identique à la valeur de `sizeof` pour les types de base.  Observons toutefois l'exemple suivant :  
  
```  
typedef struct { int a; double b; } S;  
// __alignof(S) == 8  
```  
  
 Dans ce cas, la valeur de `__alignof` est la spécification d'alignement du plus grand élément de la structure.  
  
 De même, pour  
  
```  
typedef __declspec(align(32)) struct { int a; } S;  
```  
  
 `__alignof(S)` est égal à `32`.  
  
 `__alignof` peut par exemple servir de paramètre à une de vos propres routines d'allocation de mémoire.  Par exemple, dans la structure définie `S`suivante, vous pouvez appeler une routine d'allocation de mémoire nommée `aligned_malloc` pour allouer la mémoire sur une limite d'alignement particulière.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Pour plus d'informations sur la modification de l'alignement, consultez :  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_unaligned](../cpp/unaligned.md)  
  
-   [\/Zp \(Alignement des membres de la structure\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Exemples d'alignement de structure](../build/examples-of-structure-alignment.md) \(spécifique à x64\)  
  
 Pour plus d'informations sur les différences d'alignement dans le code pour x86 et x64, consultez :  
  
-   [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)