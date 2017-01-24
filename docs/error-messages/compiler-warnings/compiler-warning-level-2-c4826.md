---
title: "Avertissement du compilateur (niveau 2) C4826 | Microsoft Docs"
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
  - "C4826"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4826"
ms.assetid: 286f5c1d-8c14-43f7-aaa6-a891db2fdc64
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4826
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La conversion de 'type1' en 'type\_2' est de type signe étendu.Cela peut provoquer un comportement inattendu au moment de l'exécution.  
  
 Cet avertissement indique que le compilateur a exécuté une extension de signature lorsqu'une opération de cast a transformé un pointeur 32 bits en une variable 64 bits.  
  
 Si l'extension a été exécutée sur un type de HANDLE Windows, il vaut mieux ignorer cet avertissement.  Si l'extension a été exécutée sur un type pointeur, vous devez modifier le cast pour empêcher l'extension de signature \(voir l'exemple ci\-dessous\).  
  
 C4826 est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4826 :  
  
```  
// C4826.cpp  
// compile with: /W2 /c  
#include <windows.h>  
#pragma warning(default: 4826)  
  
void * __ptr64 F1 (void * __ptr32 P ) {  
   return (void * __ptr64)P;   // C4826  
   // try the following line instead  
   // return (void * __ptr64)(ULONGLONG)(ULONG)P;  
}  
  
void * __ptr64 F2 ( void * P ) {  
   return (void * __ptr64)P;   // C4826  
   // try the following line instead  
   // return (void * __ptr64)(ULONGLONG)(ULONG)P;  
}  
  
unsigned __int64 F3r ( void * P ) {  
   return (unsigned __int64)P;   // C4826  
   // try the following line instead  
   // return (unsigned __int64)(ULONGLONG)(ULONG)P;  
}  
```