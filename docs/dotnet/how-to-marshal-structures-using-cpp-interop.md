---
title: "Comment&#160;: marshaler des structures &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "interopérabilité C++, structures"
  - "marshaling de données (C++), structures"
  - "Interop (C++), structures"
  - "marshaling (C++), structures"
  - "structures (C++), marshaling"
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des structures &#224; l&#39;aide de l&#39;interop&#233;rabilit&#233; C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique illustre une facette de l'interopérabilité Visual C\+\+.  Pour plus d'informations, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 Les exemples de code suivants utilisent les directives \#pragma [managé, non managé](../preprocessor/managed-unmanaged.md) pour implémenter des fonctions managées et non managées dans le même fichier, mais ces fonctions interagissent de la même manière si elles sont définies dans des fichiers séparés.  Les fichiers qui contiennent uniquement des fonctions non managées ne doivent pas être compilés avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant illustre le passage d'une structure d'une fonction managée à une fonction non managée, à la fois par valeur et par référence.  Comme la structure de cet exemple contient uniquement des types de données intrinsèques simples \(consultez [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), aucun marshaling spécial n'est requis.  Pour marshaler des structures non blittables, telles que celles qui contiennent des pointeurs, consultez [Comment : marshaler des pointeurs incorporés à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
```  
// PassStruct1.cpp  
// compile with: /clr  
  
#include <stdio.h>  
#include <math.h>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
struct Location {  
   int x;  
   int y;  
};  
  
double GetDistance(Location loc1, Location loc2) {  
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   printf_s("[unmanaged] Initializing location...\n");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma managed  
  
int main() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
## Exemple  
 L'exemple suivant illustre le passage d'une structure d'une fonction non managée à une fonction managée, à la fois par valeur et par référence.  Comme la structure de cet exemple contient uniquement des types de données intrinsèques simples \(consultez [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), aucun marshaling spécial n'est requis.  Pour marshaler des structures non blittables, telles que celles qui contiennent des pointeurs, consultez [Comment : marshaler des pointeurs incorporés à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
```  
// PassStruct2.cpp  
// compile with: /clr  
#include <stdio.h>  
#include <math.h>  
using namespace System;  
  
// native structure definition  
struct Location {  
   int x;  
   int y;  
};  
  
#pragma managed  
  
double GetDistance(Location loc1, Location loc2) {  
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);  
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);  
  
   double h = loc1.x - loc2.x;  
   double v = loc1.y = loc2.y;  
   double dist = sqrt( pow(h,2) + pow(v,2) );  
  
   return dist;  
}  
  
void InitLocation(Location* lp) {  
   Console::WriteLine("[managed] Initializing location...");  
   lp->x = 50;  
   lp->y = 50;  
}  
  
#pragma unmanaged  
  
int UnmanagedFunc() {  
   Location loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   Location loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);  
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);  
  
   double dist = GetDistance(loc1, loc2);  
   printf_s("[unmanaged] distance = %f\n", dist);  
  
   Location loc3;  
   InitLocation(&loc3);  
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);  
  
    return 0;  
}  
  
#pragma managed  
  
int main() {  
   UnmanagedFunc();  
}  
```  
  
## Voir aussi  
 [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)