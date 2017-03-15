---
title: "Acc&#232;s aux donn&#233;es C ou C++ dans les blocs __asm | Microsoft Docs"
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
  - "__asm (mot clé) (C++), données membres"
  - "accès aux données (C++), in __asm (blocs)"
  - "données membres (C++), in __asm (blocs)"
  - "types de structures dans les blocs __asm"
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Acc&#232;s aux donn&#233;es C ou C++ dans les blocs __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 L'un des principaux avantages offerts par l'assembleur inline est la capacité à faire référence à des variables C ou C\+\+ par nom.  Un bloc `__asm` peut faire référence à n'importe quel symbole, y compris des noms de variables, qui figure dans la portée où le bloc apparaît.  Par exemple, si la variable C `var` est dans la portée, l'instruction  
  
```  
__asm mov eax, var  
```  
  
 stocke la valeur de `var` dans EAX.  
  
 Si un membre de classe, de structure ou d'union a un nom unique, un bloc `__asm` peut y faire référence en utilisant seulement le nom du membre, sans spécifier la variable ou le nom `typedef` avant l'opérateur point \(**.**\).  En revanche, si le nom du membre n'est pas unique, vous devez placer une variable ou un nom `typedef` juste avant l'opérateur point.  Par exemple, les types structure de l'exemple suivant partagent `same_name` comme nom de membre :  
  
 Si vous déclarez des variables avec les types  
  
```  
struct first_type hal;  
struct second_type oat;  
```  
  
 toutes les références au membre `same_name` doivent utiliser le nom de la variable, car `same_name` n'est pas unique.  Cependant, le membre `weasel` ayant un nom unique, vous pouvez y faire référence en utilisant uniquement son nom de membre :  
  
```  
// InlineAssembler_Accessing_C_asm_Blocks.cpp  
// processor: x86  
#include <stdio.h>  
struct first_type  
{  
   char *weasel;  
   int same_name;  
};  
  
struct second_type  
{  
   int wonton;  
   long same_name;  
};  
  
int main()  
{  
   struct first_type hal;  
   struct second_type oat;  
  
   __asm  
   {  
      lea ebx, hal  
      mov ecx, [ebx]hal.same_name ; Must use 'hal'  
      mov esi, [ebx].weasel       ; Can omit 'hal'  
   }  
   return 0;  
}  
```  
  
 Notez que l'omission du nom de la variable est simplement une pratique de codage.  Les mêmes instructions assembleur sont générées, que le nom de la variable soit présent ou non.  
  
 Vous pouvez accéder aux données membres en C\+\+ sans tenir compte des restrictions d'accès.  En revanche, vous ne pouvez pas appeler de fonctions membres.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)