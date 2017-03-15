---
title: "Consid&#233;rations relatives &#224; l&#39;&#233;criture du code de prologue/&#233;pilogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__LOCAL_SIZE (constante)"
  - "code d'épilogue"
  - "code du prologue"
  - "disposition de la frame de pile"
  - "pile, disposition de la frame de pile"
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Consid&#233;rations relatives &#224; l&#39;&#233;criture du code de prologue/&#233;pilogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Avant d'écrire vos propres séquences de code de prologue et d'épilogue, il importe de comprendre comment le frame de pile est disposé.  Il est également utile de savoir utiliser le symbole **\_\_LOCAL\_SIZE**.  
  
##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Disposition du frame de pile  
 Cet exemple montre le code de prologue standard qui peut apparaître dans une fonction 32 bits :  
  
```  
push        ebp                ; Save ebp  
mov         ebp, esp           ; Set stack frame pointer  
sub         esp, localbytes    ; Allocate space for locals  
push        <registers>        ; Save registers  
```  
  
 La variable `localbytes` représente le nombre d'octets nécessaires sur la pile pour les variables locales. La variable `<registers>` est un espace réservé qui représente la liste de registres à enregistrer sur la pile.  Après avoir effectué un push des registres, vous pouvez placer toutes les autres données pertinentes sur la pile.  Voici le code d'épilogue correspondant :  
  
```  
pop         <registers>   ; Restore registers  
mov         esp, ebp      ; Restore stack pointer  
pop         ebp           ; Restore ebp  
ret                       ; Return from function  
```  
  
 La pile se réduit toujours \(des adresses de mémoire supérieures aux adresses de mémoire inférieures\).  Le pointeur de base \(`ebp`\) pointe vers la valeur de `ebp` qui fait l'objet d'un push.  La zone Variables locales commence à `ebp-4`.  Pour accéder aux variables locales, calculez un décalage à partir de `ebp` en soustrayant la valeur appropriée de `ebp`.  
  
##  <a name="_pluslang___local_size"></a> \_\_LOCAL\_SIZE  
 Le compilateur fournit un symbole, **\_\_LOCAL\_SIZE**, à utiliser dans le bloc assembleur inline de code de prologue de fonction.  Ce symbole est utilisé pour allouer de l'espace pour les variables locales sur le frame de pile dans le code de prologue personnalisé.  
  
 Le compilateur détermine la valeur de **\_\_LOCAL\_SIZE**.  Sa valeur représente le nombre total d'octets de toutes les variables locales définies par l'utilisateur et des variables temporaires générées par le compilateur.  La constante **\_\_LOCAL\_SIZE** peut être utilisée uniquement comme opérande immédiat. Elle ne peut pas être utilisée dans une expression.  Vous ne devez pas modifier ou redéfinir la valeur de ce symbole.  Par exemple :  
  
```  
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov        eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 L'exemple suivant d'une fonction naked contenant des séquences de prologue et d'épilogue personnalisées utilise le symbole **\_\_LOCAL\_SIZE** dans la séquence de prologue :  
  
```  
// the__local_size_symbol.cpp  
// processor: x86  
__declspec ( naked ) int main() {  
   int i;  
   int j;  
  
   __asm {      /* prolog */  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
   __asm {   /* epilog */  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}  
```  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Appels de fonction naked](../cpp/naked-function-calls.md)