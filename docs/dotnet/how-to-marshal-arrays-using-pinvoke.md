---
title: "Comment&#160;: marshaler des tableaux &#224; l&#39;aide de PInvoke | Microsoft Docs"
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
  - "marshaling de données (C++), tableaux"
  - "Interop (C++), tableaux"
  - "marshaling (C++), tableaux"
  - "appel de code non managé (C++), tableaux"
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des tableaux &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment les fonctions natives qui acceptent des chaînes de style C peuvent être appelées à l'aide du <xref:System.String> de type de chaîne du CLR grâce à la prise en charge de l'appel de plateforme .NET Framework.  Les programmeurs Visual C\+\+ sont encouragés à utiliser plutôt les fonctionnalités d'interopérabilité C\+\+ \(dans la mesure du possible\), car P\/Invoke ne signale pas correctement les erreurs de compilation, n'est pas de type sécurisé et peut être fastidieux à implémenter.  Si l'API non managée se présente sous la forme d'une DLL et si le code source n'est pas disponible, P\/Invoke est votre seule option \(sinon, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)\).  
  
## Exemple  
 Comme les tableaux natifs et managés sont disposés différemment en mémoire, leur passage entre la limite managée\/non managée exige une conversion ou un marshaling.  Cette rubrique montre comment un tableau d'éléments simples \(blittables\) peut être passé aux fonctions natives à partir de code managé.  
  
 Comme c'est le cas en général pour le marshaling de données managées\/non managées, l'attribut <xref:System.Runtime.InteropServices.DllImportAttribute> permet de créer un point d'entrée managé pour chaque fonction native qui sera utilisée.  Dans le cas des fonctions qui prennent des tableaux comme arguments, l'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> doit également être utilisé pour spécifier au compilateur de quelle manière les données doivent être marshalées.  Dans l'exemple suivant, l'énumération <xref:System.Runtime.InteropServices.UnmanagedType> est utilisée pour indiquer que le tableau managé doit être marshalé en tant que tableau de style C.  
  
 Le code suivant est constitué d'un module non managé et d'un module managé.  Le module non managé est une DLL qui définit une fonction acceptant un tableau d'entiers.  Le deuxième module est une application en ligne de commande managée qui importe cette fonction, mais la définit en tant que tableau managé et utilise l'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> pour spécifier que le tableau doit être converti en tableau natif lorsqu'il est appelé.  
  
 Le module managé est compilé avec \/clr, mais \/clr:pure fonctionne également.  
  
```  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 Notez qu'aucune partie de la DLL n'est exposée au code managé à l'aide de la directive \#include traditionnelle.  En réalité, comme l'accès à la DLL est limité au moment de l'exécution, les problèmes liés aux fonctions importées à l'aide de <xref:System.Runtime.InteropServices.DllImportAttribute> ne sont pas détectés au moment de la compilation.  
  
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)