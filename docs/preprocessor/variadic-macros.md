---
title: "Macros Variadic | Microsoft Docs"
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
  - "macros variadiques (C++)"
  - "__VA_ARGS__ (spécificateur de macros variadiques)"
ms.assetid: 51e757dc-0134-4bb2-bb74-64ea5ad75134
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Macros Variadic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les macros variadic sont des macros similaires à des fonctions qui contiennent un nombre variable d'arguments.  
  
## Notes  
 Pour utiliser des macros variadic, les points de suspension peuvent être spécifiés comme argument formel final dans une définition de macro, et l'identificateur de remplacement `__VA_ARGS__` peut être utilisé dans la définition afin d'insérer des arguments supplémentaires.  `__VA_ARGS__` est remplacé par tous les arguments qui correspondent aux points de suspension, notamment les virgules entre elles.  
  
 La norme C spécifie qu'au moins un argument doit être passé aux points de suspension, pour garantir que la macro ne se résout pas à une expression avec une virgule de fin.  L'implémentation Visual C\+\+ supprime une virgule de fin si aucun argument n'est passé aux points de suspension.  
  
## Exemple  
  
```cpp  
// variadic_macros.cpp  
#include <stdio.h>  
#define EMPTY  
  
#define CHECK1(x, ...) if (!(x)) { printf(__VA_ARGS__); }  
#define CHECK2(x, ...) if ((x)) { printf(__VA_ARGS__); }  
#define CHECK3(...) { printf(__VA_ARGS__); }  
#define MACRO(s, ...) printf(s, __VA_ARGS__)  
  
int main() {  
    CHECK1(0, "here %s %s %s", "are", "some", "varargs1(1)\n");  
    CHECK1(1, "here %s %s %s", "are", "some", "varargs1(2)\n");   // won't print  
  
    CHECK2(0, "here %s %s %s", "are", "some", "varargs2(3)\n");   // won't print  
    CHECK2(1, "here %s %s %s", "are", "some", "varargs2(4)\n");  
  
    // always invokes printf in the macro  
    CHECK3("here %s %s %s", "are", "some", "varargs3(5)\n");  
  
    MACRO("hello, world\n");  
  
    MACRO("error\n", EMPTY); // would cause error C2059, except VC++   
                             // suppresses the trailing comma  
}  
```  
  
## Sortie  
  
```  
here are some varargs1(1)  
here are some varargs2(4)  
here are some varargs3(5)  
hello, world  
error  
  
```  
  
## Voir aussi  
 [Macros](../preprocessor/macros-c-cpp.md)