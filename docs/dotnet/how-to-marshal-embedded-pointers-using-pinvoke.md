---
title: "Comment&#160;: marshaler des pointeurs incorpor&#233;s &#224; l&#39;aide de PInvoke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshaling de données (C++), pointeurs incorporés"
  - "pointeurs incorporés (C++)"
  - "Interop (C++), pointeurs incorporés"
  - "marshaling (C++), pointeurs incorporés"
  - "appel de code non managé (C++), pointeurs incorporés"
ms.assetid: f12c1b9a-4f82-45f8-83c8-3fc9321dbb98
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Comment&#160;: marshaler des pointeurs incorpor&#233;s &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fonctions implémentées dans des DLL non managées peuvent être appelées à partir du code managé à l'aide de la fonctionnalité d'appel de code non managé \(P\/Invoke\).  Si le code source de la DLL n'est pas disponible, P\/Invoke est la seule possibilité d'interaction.  Toutefois, contrairement aux autres langages .NET, Visual C\+\+ offre une alternative à P\/Invoke.  Pour plus d’informations, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md) et [Comment : marshaler des pointeurs incorporés à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md).  
  
## Exemple  
 Le passage de structures au code natif exige la création d'une structure managée dont le format de données équivaut à celui de la structure native.  Toutefois, les structures qui contiennent des pointeurs requièrent une gestion spéciale.  Pour chaque pointeur incorporé dans la structure native, la version managée de la structure doit contenir une instance du type <xref:System.IntPtr>.  En outre, de la mémoire doit être allouée, initialisée et libérée explicitement pour ces instances à l'aide des méthodes  <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A>, <xref:System.Runtime.InteropServices.Marshal.StructureToPtr%2A> et <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A>.  
  
 Le code suivant est constitué d'un module non managé et d'un module managé.  Le module non managé est une DLL qui définit une fonction acceptant une structure appelée ListString qui contient un pointeur, ainsi qu'une fonction appelée TakesListStruct.  Le module managé est une application en ligne de commande qui importe la fonction TakesListStruct et définit une structure appelée MListStruct équivalant au ListStruct natif, mais où le double\* est représenté par une instance de <xref:System.IntPtr>.  Avant d'appeler TakesListStruct, la fonction principale alloue et initialise la mémoire référencée par ce champ.  
  
 Le module managé est compilé avec \/clr, mais \/clr:pure fonctionne également.  
  
```  
// TraditionalDll6.cpp  
// compile with: /EHsc /LD  
#include <stdio.h>  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
#pragma pack(push, 8)  
struct ListStruct {  
   int count;  
   double* item;  
};  
#pragma pack(pop)  
  
extern "C" {  
   TRADITIONALDLL_API void TakesListStruct(ListStruct);  
}  
  
void TakesListStruct(ListStruct list) {  
   printf_s("[unmanaged] count = %d\n", list.count);  
   for (int i=0; i<list.count; i++)  
      printf_s("array[%d] = %f\n", i, list.item[i]);  
}  
```  
  
```  
// EmbeddedPointerMarshalling.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Sequential, Pack=8)]  
value struct MListStruct {  
   int count;  
   IntPtr item;  
};  
  
value struct TraditionalDLL {  
    [DllImport("TraditionalDLL6.dll")]  
   static public void TakesListStruct(MListStruct);  
};  
  
int main() {  
   array<double>^ parray = gcnew array<double>(10);  
   Console::WriteLine("[managed] count = {0}", parray->Length);  
  
   Random^ r = gcnew Random();  
   for (int i=0; i<parray->Length; i++) {  
      parray[i] = r->NextDouble() * 100.0;  
      Console::WriteLine("array[{0}] = {1}", i, parray[i]);  
   }  
  
   int size = Marshal::SizeOf(double::typeid);  
   MListStruct list;  
   list.count = parray->Length;  
   list.item = Marshal::AllocCoTaskMem(size * parray->Length);  
  
   for (int i=0; i<parray->Length; i++) {  
      IntPtr t = IntPtr(list.item.ToInt32() + i * size);  
      Marshal::StructureToPtr(parray[i], t, false);  
   }  
  
   TraditionalDLL::TakesListStruct( list );  
   Marshal::FreeCoTaskMem(list.item);  
}  
```  
  
 Notez qu'aucune partie de la DLL n'est exposée au code managé à l'aide de la directive \#include traditionnelle.  En réalité, l'accès à la DLL se limite au moment de l'exécution. Par conséquent, les problèmes liés aux fonctions importées à l'aide de <xref:System.Runtime.InteropServices.DllImportAttribute> ne sont pas détectés au moment de la compilation.  
  
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)