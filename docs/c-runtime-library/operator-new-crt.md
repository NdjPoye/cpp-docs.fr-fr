---
title: "op&#233;rateur new(CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "opérateur new[]"
  - "new (vecteur)"
ms.assetid: 4ae51618-a4e6-4172-b324-b99d86d1bdca
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# new, op&#233;rateur (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alloue un bloc de mémoire à partir du segment de mémoire.  
  
## Syntaxe  
  
```  
  
      void *__cdecl operator new(  
   size_t count  
);  
void *__cdecl operator new(  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new(  
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
 Cette forme de`operator new` est reconnue comme un nouveau scalaire, à l'inverse de la forme de nouveaux vecteurs\([operator new&#91;&#93;](../c-runtime-library/new-operator-crt.md)\).  
  
 La première forme de cet opérateur est connue comme la forme de non placement.  La seconde forme de cet opérateur est connu comme la forme de placement et la troisième forme de cet opérateur est la forme de placement "nonthrowing".  
  
 La première forme de l'opérateur est définie par le compilateur et ne requiert pas d'inclure new.h dans votre programme.  
  
 [opérateur delete](../c-runtime-library/operator-delete-crt.md) libère de la mémoire allouée à `operator new`.  
  
 Vous pouvez configurer si operator retourne null ou relève une exception en cas de échec.  Consultez [Les Opérateurs nouveau supprimer](../cpp/new-and-delete-operators.md) pour plus d'informations.  
  
 À l'exception des comportements throwing et no\-throwing , le CRT `operator new` se comporte comme [operator new&#91;&#93;](../Topic/operator%20new%20\(%3Cnew%3E\).md) dans la librairie C\+\+ standard.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**new**|\<new.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 L'exemple suivant indique comment utiliser la frome scalaire, nonplacement de `operator new`.  
  
```  
// crt_new1.cpp  
#include <stdio.h>  
int main() {  
   int * i = new int(6);  
   printf("%d\n", *i);  
   delete i;  
}  
```  
  
 L'exemple suivant indique comment utiliser la frome scalaire, placement de `operator new`.  
  
```  
// crt_new2.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int(12);  
   printf("*i = %d\n", *i);  
   // initialize existing memory (i) with, in this case, int(7)  
   int * j = new(i) int(7);   // placement new  
   printf("*j = %d\n", *j);  
   printf("*i = %d\n", *i);  
   delete i;   // or, could have deleted j  
}  
```  
  
 L'exemple suivant indique comment utiliser la frome scalaire, de placement, et no throw de `operator new`.  
  
```  
// crt_new3.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   // allocates memory, initialize (8) and if call fails, new returns null  
   int * k = new(std::nothrow) int(8);   // placement new  
   printf("%d\n", *k);  
   delete k;  
}  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)