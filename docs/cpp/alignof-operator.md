---
title: "opérateur __alignof | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- alignas_cpp
- __alignof_cpp
- alignof_cpp
dev_langs: C++
helpviewer_keywords:
- alignas [C++]
- alignment of structures
- __alignof keyword [C++]
- alignof [C++]
- types [C++], alignment requirements
ms.assetid: acb1eed7-6398-40bd-b0c5-684ceb64afbc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 50a8d6e524847d46d62b5f1da134332f35edcf92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="alignof-operator"></a>__alignof, opérateur
C++11 présente l'opérateur `alignof` qui retourne l'alignement, en octets, du type spécifié. Pour une portabilité maximale, vous devez utiliser l'opérateur alignof au lieu de l'opérateur __alignof spécifique à Microsoft.  
  
 **Section spécifique à Microsoft**  
  
 Retourne une valeur de type **size_t** qui est la spécification d’alignement du type.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      __alignof(   
   type    
)  
```  
  
## <a name="remarks"></a>Notes  
 Exemple :  
  
|Expression|Value|  
|----------------|-----------|  
|**__alignof (char)**|1|  
|**__alignof (short)**|2|  
|**__alignof (int)**|4|  
|**__alignof ( \__int64)**|8|  
|**__alignof (float)**|4|  
|**__alignof (double)**|8|  
|**__alignof (char\* )**|4|  
  
 La valeur de `__alignof` est identique à la valeur de `sizeof` pour les types de base. Observons toutefois l'exemple suivant :  
  
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
  
 `__alignof` peut par exemple servir de paramètre à une de vos propres routines d'allocation de mémoire. Par exemple, dans la structure définie `S`suivante, vous pouvez appeler une routine d'allocation de mémoire nommée `aligned_malloc` pour allouer la mémoire sur une limite d'alignement particulière.  
  
```  
typedef __declspec(align(32)) struct { int a; double b; } S;  
int n = 50; // array size  
S* p = (S*)aligned_malloc(n * sizeof(S), __alignof(S));  
```  
  
 Pour plus d'informations sur la modification de l'alignement, consultez :  
  
-   [pack](../preprocessor/pack.md)  
  
-   [align](../cpp/align-cpp.md)  
  
-   [__unaligned](../cpp/unaligned.md)  
  
-   [/Zp (Alignement des membres de la structure)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Exemples d’alignement de Structure](../build/examples-of-structure-alignment.md) (x64 spécifique)  
  
 Pour plus d'informations sur les différences d'alignement dans le code pour x86 et x64, consultez :  
  
-   [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)