---
title: "__ptr32, __ptr64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__ptr32_cpp"
  - "__ptr64_cpp"
  - "__ptr32"
  - "__ptr64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ptr32 (mot clé) (C++)"
  - "__ptr64 (mot clé) (C++)"
  - "_ptr32 (mot clé) (C++)"
  - "_ptr64 (mot clé) (C++)"
  - "ptr32 (mot clé) (C++)"
  - "ptr64 (mot clé) (C++)"
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __ptr32, __ptr64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 `__ptr32` représente un pointeur natif sur un système 32 bits, tandis que `__ptr64` représente un pointeur natif sur un système 64 bits.  
  
 L'exemple suivant montre comment déclarer chacun de ces types pointeur :  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 Sur un système 32 bits, un pointeur déclaré avec `__ptr64` est tronqué à un pointeur 32 bits.  Sur un système 64 bits, un pointeur déclaré avec `__ptr32` est converti en pointeur 64 bits.  
  
> [!NOTE]
>  Vous ne pouvez pas utiliser `__ptr32` ou `__ptr64` lors de la compilation avec **\/clr:pure**.  Sinon, l'erreur `Compiler Error C2472` est générée.  
  
## Exemple  
 L'exemple suivant montre comment déclarer et allouer des pointeurs avec les mots clés `__ptr32` et `__ptr64`.  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
  **32**  
**64**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)