---
title: "Avertissement du compilateur (niveau&#160;4) C4754 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4754"
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 6
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les règles de conversion pour les opérations arithmétiques dans une comparaison signifient qu'une branche ne peut pas être exécutée.  
  
 L'avertissement C4754 est publié car le résultat de la comparaison est toujours identique.  Cela indique qu'une des branches de la condition n'est jamais exécuté, très probablement parce que l'expression entière associée est incorrecte.  Cette erreur de code se produit souvent dans les contrôles incorrects de dépassement sur les entiers sur les architectures 64 bits.  
  
 Les règles de conversion entières sont complexes et il y a de nombreuses pièges subtils.  Comme alternative à résoudre chaque avertissement C4754, il vous est possible de mettre à jour le code pour utiliser [Bibliothèque SafeInt](../../windows/safeint-library.md).  
  
## Exemple  
 Cet exemple génère l'erreur C4754 :  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 L'addition `a + b` peut provoquer un dépassement de capacité arithmétiques avant le résultat est upcast à une valeur 64 bits et assigné à la variable `x`64 bits.  Cela signifie que le contrôle sur `x` est redondant et n'intercepte jamais un dépassement de capacité.  Dans ce cas, le compilateur émet cet avertissement :  
  
  **Avertissement C4754 : Modalités de conversion pour les opérations arithmétiques dans la comparaison au moyen de C4754a.cpp \(7\) qu'une branche ne peut pas être exécuté.  Cast de '\(a \+ ...\)' vers 'ULONG64' \(ou un type similaire de 8 octets\).**  Pour éliminer l'avertissement, il vous est possible de modifier l'instruction d'assignation pour effectuer un cast des opérandes à 8 valeurs d'octets :  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## Exemple  
 L'exemple suivant génère également l'erreur C4754.  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 L'opérateur `sizeof()` renvoie un `size_t`, dont la taille est architecture\- dépendant.  L'exemple de code fonctionne sur les architectures 32 bits où `size_t` est un type 32 bits.  Toutefois, dans les architectures 64 bits, `size_t` est un type 64 bits.  Les règles de conversion pour les entiers signifient que `a` est upcast à une valeur 64 bits dans l'expression `a + b < a` comme c'était écrit `(size_t)a + (size_t)b < (size_t)a`.  Lorsque `a` et `b` sont des entiers 32 bits, l'opération 64 bits d'ajout peut jamais déborder, et les blocages ne tiennent jamais.  Par conséquent, le code ne détecte jamais une condition de dépassement sur les entiers sur les architectures 64 bits.  Cet exemple fait le compilateur à émettre cet avertissement :  
  
  **Avertissement C4754 : Modalités de conversion pour les opérations arithmétiques dans la comparaison au moyen de C4754a.cpp \(7\) signifient qu'une branche ne peut pas être exécuté.  Cast '4' et 'ULONG' \(ou en type similaire de 4 octets\).**  Notez que le message d'avertissement répertorie explicitement la valeur de constante 4 au lieu de la source d'origine chaîne\- par le temps que l'analyse d'avertissement rencontre code incriminée qui a été `sizeof(unsigned long)`, a déjà été converti en une constante.  Par conséquent, il vous est possible d'avoir à trouver quelle expression dans le code source est associé à la valeur de constante dans le message d'avertissement.  Les sources les plus courantes de code résolues aux constantes dans les messages d'avertissement C4754 sont des expressions telles que `sizeof(TYPE)` et `strlen(szConstantString)`.  
  
 Dans ce cas, le code fixe ressemblerait à ceci :  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **Notes** Numéro de ligne prévue des avertissements du compilateur est la dernière ligne d'une instruction.  Dans un message d'avertissement concernant une instruction conditionnelle complexe qui est plusieurs lignes réparties, la ligne comportant l'erreur de code peut être plusieurs lignes avant la ligne qui est signalée.  Par exemple :  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
  
```