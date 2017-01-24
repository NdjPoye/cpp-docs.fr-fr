---
title: "&#201;criture de fonctions avec un assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), dans les fonctions"
  - "assembleur (C++), écrire des fonctions"
  - "fonctions (C++), assembleur inline"
  - "assembleur inline (C++), écrire des fonctions"
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &#201;criture de fonctions avec un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 Si vous écrivez une fonction avec le code assembleur inline, il est facile de passer des arguments à la fonction et retourner une valeur à partir de celui\-ci.  Les exemples suivants comparent une fonction tout d'abord écrit pour un assembleur distinct et ré\-écrites pour l'assembleur inline.  La fonction appelée  `power2`, qui reçoit deux paramètres, en multipliant le premier paramètre par 2 à la puissance du second paramètre.  Écrit pour un assembleur distinct, la fonction peut se présenter comme suit :  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 Dans la mesure où il est écrit pour un assembleur distinct, la fonction requiert une source distincte fichier et assembly et lier les étapes.  Généralement, les arguments de fonction C et C\+\+ sont passés sur la pile, par conséquent, cette version de la  `power2`fonction accède à ses arguments par leur position dans la pile.  \(Notez que les  **modèle** disponible dans MASM et certains autres assembleurs, de la directive vous permet également d'accéder aux arguments de la pile et des variables de pile locales par son nom.\)  
  
## Exemple  
 Ce programme écrit les  `power2`fonction avec le code assembleur inline :  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 La version en ligne de la  `power2`fonction fait référence à ses arguments par nom et s'affiche dans le même fichier source que le reste du programme.  Cette version nécessite également moins instructions d'assemblage.  
  
 Dans la mesure où la version en ligne du  `power2`n'exécute pas un C  `return`instruction, il génère un avertissement sans danger si vous compilez au niveau d'avertissement 2 ou version ultérieure.  La fonction retourne une valeur, mais le compilateur ne peut pas savoir qui en l'absence d'une  `return`instruction.  Vous pouvez utiliser  [\#pragma warning](../../preprocessor/warning.md) pour désactiver la génération de cet avertissement.  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation de C ou C\+\+ dans les blocs \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)