---
title: "Appel de fonctions C dans un assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), appeler des fonctions"
  - "appels de fonction, fonctions C"
  - "appels de fonction, dans l'assembleur inline"
  - "fonctions (C), appeler dans l'assembleur inline"
  - "assembleur inline, appeler des fonctions"
  - "Visual C, fonctions"
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Appel de fonctions C dans un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Un bloc `__asm` peut appeler des fonctions C, y compris des routines de bibliothèques C.  L'exemple suivant appelle la routine de bibliothèque `printf` :  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 Les arguments de fonction étant passés sur la pile, il vous suffit d'effectuer un push des arguments nécessaires \(pointeurs de chaîne, dans l'exemple précédent\) avant d'appeler la fonction.  Les arguments font l'objet d'un push dans l'ordre inverse ; ils sont donc dépilés dans l'ordre souhaité.  Pour émuler l'instruction C  
  
```  
printf( format, hello, world );  
```  
  
 l'exemple envoie les pointeurs vers `world`, `hello` et `format`, dans cet ordre\-là, puis appelle `printf`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)