---
title: "Avertissement du compilateur (niveau&#160;4) C4703 | Microsoft Docs"
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
  - "C4703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4703"
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;4) C4703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La variable 'nom' à pointeur locale potentiellement non initialisée est utilisée.  
  
 La variable à pointeur locale *name* a pu être utilisée sans s'être vue affecter une valeur.  Cela peut générer des résultats imprévisibles.  
  
## Exemple  
 Le code suivant génère C4701 et C4703.  
  
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
  
  **c:\\src\\test.cpp\(10\) : avertissement C4701 : la variable locale éventuellement non initialisée 'p' est utilisée**  
 **c:\\src\\test.cpp\(10\) : avertissement C4703 : le pointeur local éventuellement non initialisé 'p' est utilisé** Pour corriger cet avertissement, initialisez la variable comme indiqué dans l'exemple suivant :  
  
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
 [Avertissement du compilateur \(niveau 4\) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)   
 [Avertissements, \/sdl et l'amélioration de la détection de variables non initialisées](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)