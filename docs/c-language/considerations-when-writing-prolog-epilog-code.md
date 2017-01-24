---
title: "Consid&#233;rations relatives &#224; l&#39;&#233;criture du code de prologue/&#233;pilogue | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "__LOCAL_SIZE (constante)"
  - "dispositions, frame de pile"
  - "disposition de la frame de pile"
  - "pile, disposition de la frame de pile"
ms.assetid: 3b8addec-e809-48e4-b1d0-5bad133bd4b8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Consid&#233;rations relatives &#224; l&#39;&#233;criture du code de prologue/&#233;pilogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Avant d'écrire vos propres séquences de code de prologue et d'épilogue, il importe de comprendre comment le frame de pile est disposé.  Il est également utile de savoir utiliser la constante prédéfinie **\_\_LOCAL\_SIZE**.  
  
##  <a name="_clang_c_stack_frame_layout"></a> Disposition du frame de pile C  
 Cet exemple montre le code de prologue standard qui peut apparaître dans une fonction 32 bits :  
  
```  
push     ebp                 ; Save ebp  
mov      ebp, esp            ; Set stack frame pointer  
sub      esp, localbytes     ; Allocate space for locals  
push     <registers>         ; Save registers  
```  
  
 La variable `localbytes` représente le nombre d'octets nécessaires sur la pile pour les variables locales. La variable `registers` est un espace réservé qui représente la liste de registres à enregistrer sur la pile.  Après avoir effectué un push des registres, vous pouvez placer toutes les autres données pertinentes sur la pile.  Voici le code d'épilogue correspondant :  
  
```  
pop      <registers>         ; Restore registers  
mov      esp, ebp            ; Restore stack pointer  
pop      ebp                 ; Restore ebp  
ret                          ; Return from function  
```  
  
 La pile se réduit toujours \(des adresses de mémoire supérieures aux adresses de mémoire inférieures\).  Le pointeur de base \(`ebp`\) pointe vers la valeur de `ebp` qui fait l'objet d'un push.  La zone de variables locales commence à `ebp-2`.  Pour accéder aux variables locales, calculez un décalage à partir de `ebp` en soustrayant la valeur appropriée de `ebp`.  
  
##  <a name="_clang_the___local_size_constant"></a> La constante \_\_LOCAL\_SIZE  
 Le compilateur fournit une constante, **\_\_LOCAL\_SIZE**, à utiliser dans le bloc assembleur inline de code de prologue de fonction.  Cette constante est utilisée pour allouer de l'espace pour les variables locales sur le frame de pile dans le code de prologue personnalisé.  
  
 Le compilateur détermine la valeur de **\_\_LOCAL\_SIZE**.  Cette valeur est le nombre total d'octets de toutes les variables locales définies par l'utilisateur et des variables temporaires générées par le compilateur.  La constante **\_\_LOCAL\_SIZE** peut être utilisée uniquement comme opérande immédiat. Elle ne peut pas être utilisée dans une expression.  Vous ne devez pas modifier ou redéfinir la valeur de cette constante.  Par exemple :  
  
```  
mov      eax, __LOCAL_SIZE           ;Immediate operand--Okay  
mov      eax, [ebp - __LOCAL_SIZE]   ;Error  
```  
  
 L'exemple suivant d'une fonction naked contenant des séquences de prologue et d'épilogue personnalisées utilise **\_\_LOCAL\_SIZE** dans la séquence de prologue :  
  
```  
__declspec ( naked ) func()  
{  
   int i;  
   int j;  
  
   __asm      /* prolog */  
      {  
      push   ebp  
      mov      ebp, esp  
      sub      esp, __LOCAL_SIZE  
      }  
  
   /* Function body */  
  
   __asm      /* epilog */  
      {  
      mov      esp, ebp  
      pop      ebp  
      ret  
      }  
}     
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Naked, fonctions](../c-language/naked-functions.md)