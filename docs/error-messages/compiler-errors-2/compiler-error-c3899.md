---
title: "Erreur du compilateur C3899 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3899"
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Erreur du compilateur C3899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : l'utilisation comme l\-value des données membres initonly n'est pas autorisée directement dans une région parallèle de la classe 'classe'  
  
 Les données membres [initonly](../../dotnet/initonly-cpp-cli.md) ne peuvent pas être initialisées à l'intérieur de la partie d'un constructeur qui se situe dans une région [parallel](../../parallel/openmp/reference/parallel.md).  Cela est dû au fait que le compilateur effectue un réadressage interne de ce code, de sorte qu'il ne fait effectivement plus partie du constructeur.  
  
 Pour résoudre ce problème, initialisez les données membres initonly dans le constructeur, mais à l'extérieur de la région parallèle.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3899 :  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```