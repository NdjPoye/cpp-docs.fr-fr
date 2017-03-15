---
title: "R&#232;gles et limitations pour l&#39;utilisation des fonctions naked | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "naked (fonctions)"
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#232;gles et limitations pour l&#39;utilisation des fonctions naked
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Les règles et les limitations suivantes s'appliquent aux fonctions naked :  
  
-   L'instruction `return` n'est pas autorisée.  
  
-   Les constructions de gestion structurée des exceptions et de gestion des exceptions C\+\+ ne sont pas autorisées, car elles doivent se dérouler sur le frame de pile.  
  
-   Pour la même raison, toute forme de `setjmp` est interdite.  
  
-   L'utilisation de la fonction `_alloca` est interdite.  
  
-   Pour s'assurer qu'aucun code d'initialisation de variables locales n'apparaît avant la séquence de prologue, les variables locales initialisées ne soient pas autorisées dans la portée de la fonction.  En particulier, la déclaration d'objets C\+\+ n'est pas autorisée dans la portée de la fonction.  En revanche, il peut y avoir des données initialisées dans une portée imbriquée.  
  
-   L'optimisation du pointeur de frame \(option du compilateur \/Oy\) n'est pas recommandée, mais elle est supprimée automatiquement pour une fonction naked.  
  
-   Vous ne pouvez pas déclarer d'objets de classe C\+\+ dans la portée lexicale de fonction.  Vous pouvez toutefois déclarer des objets dans un bloc imbriqué.  
  
-   Le mot clé `naked` est ignoré lors de la compilation avec [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
-   Pour les fonctions naked [\_\_fastcall](../cpp/fastcall.md), chaque fois qu'il y a une référence dans du code C\/C\+\+ à l'un des arguments de registre, le code de prologue doit stocker les valeurs de ce registre à l'emplacement de pile correspondant à cette variable.  Par exemple :  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Appels de fonction naked](../cpp/naked-function-calls.md)