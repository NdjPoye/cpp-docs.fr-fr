---
title: "op&#233;rateur new(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "new[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "opérateur new[]"
  - "new (vecteur)"
ms.assetid: 79682f85-6889-40f6-b8f7-9eed5176ea35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# op&#233;rateur new(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alloue un bloc de mémoire à partir du tas.  
  
## Syntaxe  
  
```  
  
      void *__cdecl operator new[](size_t count);  
void *__cdecl operator new[] (  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new[] (  
   size_t count,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Paramètres  
 *count*  
 Taille de l'allocation.  
  
 *object*  
 Pointeur vers un bloc de mémoire dans lequel l'objet est créé.  
  
## Valeur de retour  
 Un pointeur vers l'adresse ayant le moins d'octets de la mémoire nouvellement allouée.  
  
## Notes  
 Cette forme de`operator new` est appelé nouveau vecteur, à l'inverse de la forme nouveau scalaire \([opérateur nouveau](../c-runtime-library/operator-new-crt.md)\).  
  
 La première forme de cet opérateur est connue comme la forme de non placement.  La seconde forme de cet opérateur est connu comme la forme de placement et la troisième forme de cet opérateur est la forme de placement "nonthrowing".  
  
 La première forme de l'opérateur est définie par le compilateur et ne requiert pas d'inclure new.h dans votre programme.  
  
 [operator delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) supprimer libère de la mémoire avec l'opérateur nouveau.  
  
 Vous pouvez configurer si `operator new[]` retourne null ou lève une exception en cas de échec.  Consultez [Les Opérateurs nouveau supprimer](../cpp/new-and-delete-operators.md) pour plus d'informations.  
  
 À l'exception des comportements throwing et no\-throwing , l' `operator new` CRT se comporte comme [operator new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) dans la librairie C\+\+ standard.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`new[]`|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 L'exemple suivant indique comment utiliser la frome vectorielle, sans placement de `operator new`.  
  
```  
// crt_new4.cpp  
#include <stdio.h>  
int main() {  
   int * k = new int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
 L'exemple suivant indique comment utiliser la frome vectorielle, avec placement de `operator new`.  
  
```  
// crt_new5.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int[10];  
   i[0] = 21;  
   printf("%d\n", i[0]);  
   // initialize existing memory (i) with, in this case, int[[10]  
   int * j = new(i) int[10];   // placement vector new  
   printf("%d\n", j[0]);  
   j[0] = 22;  
   printf("%d\n", i[0]);  
   delete [] i;   // or, could have deleted [] j   
}  
```  
  
 L'exemple suivant indique comment utiliser la frome vectorielle, sans placement, et no throw de `operator new`.  
  
```  
// crt_new6.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * k = new(std::nothrow) int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
## Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)