---
title: "Comment&#160;: marshaler des pointeurs incorpor&#233;s &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interopérabilité C++, pointeurs incorporés"
  - "marshaling de données (C++), pointeurs incorporés"
  - "Interop (C++), pointeurs incorporés"
  - "marshaling (C++), pointeurs incorporés"
  - "pointeurs (C++), marshaling"
  - "structures (C++), marshaling de pointeurs incorporés"
ms.assetid: 05fb8858-97f2-47aa-86b2-2c0ad713bdb2
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des pointeurs incorpor&#233;s &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais ces fonctions interagissent de la même manière si elles sont définies dans des fichiers séparés.  Les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant montre comment une fonction non managée qui prend une structure contenant des pointeurs peut être appelée à partir d'une fonction managée.  La fonction managée crée une instance de la structure et initialise le pointeur incorporé avec le mot clé new \(plutôt que le mot clé [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md)\).  Comme cette opération alloue la mémoire sur le tas natif, il n'est pas nécessaire d'épingler le tableau pour supprimer le garbage collection.  Toutefois, la mémoire doit être supprimée explicitement pour éviter toute fuite de mémoire.  
  
```  
// marshal_embedded_pointer.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// unmanaged struct  
struct ListStruct {  
   int count;  
   double* item;  
};  
  
#pragma unmanaged  
  
void UnmanagedTakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
  
#pragma managed  
  
int main() {  
   ListStruct list;  
   list.count = 10;  
   list.item = new double[list.count];  
  
   Console::WriteLine("[managed] count = {0}", list.count);  
   Random^ r = gcnew Random(0);  
   for (int i=0; i<list.count; i++) {  
      list.item[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, list.item[i]);  
   }  
  
   UnmanagedTakesListStruct( list );  
   delete list.item;  
}  
```  
  
  **\[managed\] count \= 10**  
**array\[0\] \= 72.624326996796**  
**array\[1\] \= 81.7325359590969**  
**array\[2\] \= 76.8022689394663**  
**array\[3\] \= 55.8161191436537**  
**array\[4\] \= 20.6033154021033**  
**array\[5\] \= 55.8884794618415**  
**array\[6\] \= 90.6027066011926**  
**array\[7\] \= 44.2177873310716**  
**array\[8\] \= 97.754975314138**  
**array\[9\] \= 27.370445768987**  
**\[unmanaged\] count \= 10**  
**array\[0\] \= 72.624327**  
**array\[1\] \= 81.732536**  
**array\[2\] \= 76.802269**  
**array\[3\] \= 55.816119**  
**array\[4\] \= 20.603315**  
**array\[5\] \= 55.888479**  
**array\[6\] \= 90.602707**  
**array\[7\] \= 44.217787**  
**array\[8\] \= 97.754975**  
**array\[9\] \= 27.370446**   
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)