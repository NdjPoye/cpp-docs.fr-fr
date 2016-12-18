---
title: "Comment&#160;: marshaler des structures &#224; l&#39;aide de PInvoke | Microsoft Docs"
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
  - "marshaling de données (C++), structures"
  - "Interop (C++), structures"
  - "marshaling (C++), structures"
  - "appel de code non managé (C++), structures"
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
caps.latest.revision: 30
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des structures &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document explique comment les fonctions natives qui acceptent des chaînes de style C peuvent être appelées à partir de fonctions managées qui fournissent une instance de <xref:System.String> à l'aide de P\/Invoke.  Il est recommandé d'utiliser les fonctionnalités d'interopérabilité C\+\+ au lieu de P\/Invoke, car P\/Invoke offre peu de rapports d'erreurs au moment de la compilation, n'est pas de type sécurisé et peut s'avérer fastidieux à implémenter ; toutefois, si l'API non managée est incluse dans un package en tant que DLL et si le code source n'est pas disponible, P\/Invoke est votre seule option.  Sinon, consultez les documents suivants :  
  
-   [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [How to: Marshal Structures Using PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
 Par défaut, les structures natives et managées sont exposées différemment en mémoire ; par conséquent, le passage correct de structures au\-delà de la limite managée\/non managée exige des étapes supplémentaires pour préserver l'intégrité des données.  
  
 Ce document explique les étapes nécessaires à la définition d'équivalents managés de structures natives et comment les structures obtenues peuvent être passées à des fonctions non managées.  Ce document suppose que des structures simples \(celles qui ne contiennent pas de chaînes ou de pointeurs\) sont utilisées.  Pour plus d'informations sur l'interopérabilité non blittable, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  P\/Invoke ne peut pas avoir de types non blittables comme valeur de retour.  Les types blittables ont la même représentation en code managé et non managé.  Pour plus d'informations, consultez [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md).  
  
 Le marshaling de structures blittables simples au\-delà de la limite managée\/non managée exige d'abord que les versions managées de chaque structure native soient définies.  Ces structures peuvent posséder tout nom autorisé ; il n'existe aucune relation entre la version native et la version managée des deux structures, à l'exception de leur format de données.  Par conséquent, il est vital que la version managée contienne des champs de la même taille et dans le même ordre que la version native. \(Il n'existe aucun mécanisme permettant de garantir que les versions managée et native de la structure sont équivalentes ; par conséquent, les incompatibilités ne deviennent visibles qu'au moment de l'exécution.  C'est le programmeur qui est chargé de garantir que les deux structures possèdent le même format de données.\)  
  
 Comme les membres de structures managées sont parfois réorganisés à des fins de performances, il est nécessaire d'utiliser l'attribut <xref:System.Runtime.InteropServices.StructLayoutAttribute> afin d'indiquer que les structures sont disposées de manière séquentielle.  Il peut également être utile de définir explicitement le paramètre de compression de structure afin qu'il soit identique à celui utilisé par la structure native \(même si Visual C\+\+ utilise par défaut une compression de structure de 8 octets pour les deux codes managés\).  
  
1.  Ensuite, utilisez <xref:System.Runtime.InteropServices.DllImportAttribute> pour déclarer des points d'entrée correspondant à toute fonction non managée qui accepte la structure, mais utilisez la version managée de la structure dans les signatures de la fonction, même si cela est discutable en cas d'utilisation du même nom pour les deux versions de la structure.  
  
2.  À présent, le code managé peut passer la version managée de la structure aux fonctions non managées comme s'il s'agissait de fonctions réellement managées.  Ces structures peuvent être passées par valeur ou par référence, comme illustré dans l'exemple suivant.  
  
## Exemple  
 Le code suivant est constitué d'un module non managé et d'un module managé.  Le module non managé est une DLL qui définit une structure appelée Location et une fonction appelée GetDistance qui accepte deux instances de la structure Location.  Le deuxième module est une application en ligne de commande managée qui importe la fonction GetDistance, mais la définit en tant qu'équivalent managé de la structure Location, MLocation.  En pratique, le même nom serait probablement utilisé pour les deux versions de la structure ; toutefois, un nom différent est utilisé ici pour montrer que le prototype DllImport est défini en tant que version managée.  
  
 Le module managé est compilé avec \/clr, mais \/clr:pure fonctionne également.  
  
 Notez qu'aucune partie de la DLL n'est exposée au code managé à l'aide de la directive \#include traditionnelle.  En réalité, l'accès à la DLL se limite au moment de l'exécution ; par conséquent, les problèmes liés aux fonctions importées à l'aide de DllImport ne sont pas détectés au moment de la compilation.  
  
```  
// TraditionalDll3.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#include <stdio.h>  
#include <math.h>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
   #define TRADITIONALDLL_API __declspec(dllexport)  
#else  
   #define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct Location {  
   int x;  
   int y;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API double GetDistance(Location, Location);  
   TRADITIONALDLL_API void InitLocation(Location*);  
}  
  
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
```  
  
## Exemple  
  
```  
// MarshalStruct_pi.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MLocation {  
   int x;  
   int y;  
};  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL3.dll")]  
   static public double GetDistance(MLocation, MLocation);  
   [DllImport("TraditionalDLL3.dll")]  
   static public double InitLocation(MLocation*);  
};  
  
int main() {  
   MLocation loc1;  
   loc1.x = 0;  
   loc1.y = 0;  
  
   MLocation loc2;  
   loc2.x = 100;  
   loc2.y = 100;  
  
   double dist = TraditionalDLL::GetDistance(loc1, loc2);  
   Console::WriteLine("[managed] distance = {0}", dist);  
  
   MLocation loc3;  
   TraditionalDLL::InitLocation(&loc3);  
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);  
}  
```  
  
  **\[unmanaged\] loc1\(0,0\) loc2\(100,100\)**  
**\[managed\] distance \= 141.42135623731**  
**\[unmanaged\] Initializing location...**  
**\[managed\] x\=50 y\=50**   
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)