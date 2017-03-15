---
title: "Avertissement du compilateur (niveau&#160;4) C4701 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4701"
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Avertissement du compilateur (niveau&#160;4) C4701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La variable locale éventuellement non initialisée 'nom' est utilisée  
  
 La variable locale *name* a pu être utilisée sans s'être vue affecté une valeur.  Cela peut générer des résultats imprévisibles.  
  
## Exemple  
 Le code suivant génère les erreurs C4701 et C4703.  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
  **c:\\src\\test.cpp\(10\) : avertissement C4701 : la variable locale potentiellement non initialisée 'p' est utilisée**  
 **c:\\src\\test.cpp\(10\) : avertissement C4703 : le pointeur local potentiellement non initialisé 'p' est utilisé** Pour corriger cet avertissement, initialisez la variable comme indiqué dans l'exemple suivant :  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## Voir aussi  
 [Avertissement du compilateur \(niveau 4\) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [Avertissements, \/sdl et l'amélioration de la détection de variables non initialisées](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)