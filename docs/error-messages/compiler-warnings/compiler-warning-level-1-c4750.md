---
title: "Avertissement du compilateur (niveau&#160;1) C4750 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4750"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4750"
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4750
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : fonction with \_alloca\(\) inline dans une boucle  
  
 La fonction 'identifier' force l’expansion inline de la fonction [\_alloca](../../c-runtime-library/reference/alloca.md) dans une boucle, ce qui peut provoquer un dépassement de capacité de la pile lors de l’exécution de la boucle.  
  
### Pour corriger cette erreur  
  
1.  Vérifiez que la fonction 'identifier' n’est pas modifiée avec le spécificateur [\_\_forceinline](../../misc/inline-inline-forceinline.md).  
  
2.  Veillez à ce que la fonction 'identifier' ne contienne pas une fonction [\_alloca](../../c-runtime-library/reference/alloca.md) contenue elle\-même dans une boucle.  
  
3.  Ne spécifiez pas le commutateur de compilation [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md), [\/Ox](../../build/reference/ox-full-optimization.md) ni [\/Og](../../build/reference/og-global-optimizations.md).  
  
4.  Placez la fonction [\_alloca](../../c-runtime-library/reference/alloca.md) dans une [instruction try\-except](../../cpp/try-except-statement.md) qui intercepte un dépassement de capacité de la pile.  
  
## Exemple  
 L’exemple de code suivant appelle `MyFunction` dans une boucle, et `MyFunction` appelle la fonction `_alloca`. Le modificateur `__forceinline` provoque l’expansion inline de la fonction `_alloca`.  
  
```  
// c4750.cpp // compile with: /O2 /W1 /c #include <intrin.h> char * volatile newstr; __forceinline void myFunction(void) // C4750 warning { // The _alloca function does not require a __try/__except // block because the example uses compiler option /c. newstr = (char * volatile) _alloca(1000); } int main(void) { for (int i=0; i<50000; i++) myFunction(); return 0; }  
```  
  
## Voir aussi  
 [\_alloca](../../c-runtime-library/reference/alloca.md)