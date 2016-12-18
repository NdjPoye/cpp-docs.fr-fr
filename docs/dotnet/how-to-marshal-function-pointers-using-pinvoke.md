---
title: "Comment&#160;: marshaler des pointeurs fonction &#224; l&#39;aide de PInvoke | Microsoft Docs"
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
  - "marshaling de données (C++), rappels et délégués"
  - "Interop (C++), rappels et délégués"
  - "marshaling (C++), rappels et délégués"
  - "appel de code non managé (C++), rappels et délégués"
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: marshaler des pointeurs fonction &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment les délégués managés peuvent être utilisés plutôt que des pointeurs fonction lors de l'interaction avec des fonctions non managées à l'aide des fonctionnalités P\/Invoke du .NET Framework.  Cependant, les programmeurs Visual C\+\+ sont encouragés à utiliser plutôt les fonctionnalités d'interopérabilité C\+\+ \(dans la mesure du possible\), car P\/Invoke signale peu les erreurs de compilation, n'est pas de type sécurisé et peut être fastidieux à implémenter.  Si l'API non managée se présente sous la forme d'une DLL et si le code source n'est pas disponible, P\/Invoke est votre seule option.  Sinon, consultez les rubriques suivantes :  
  
-   [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)  
  
-   [Comment : marshaler des rappels et des délégués à l'aide de l'interopérabilité C\+\+](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
 Les API non managées qui prennent des pointeurs de fonction comme arguments peuvent être appelés à partir du code managé avec un délégué managé plutôt que le pointeur fonction natif.  Le compilateur marshale automatiquement le délégué vers les fonctions non managées en tant que pointeur fonction et insère le code de transition managé\/non managé nécessaire.  
  
## Exemple  
 Le code suivant est constitué d'un module non managé et d'un module managé.  Le module non managé est une DLL qui définit une fonction appelée TakesCallback acceptant un pointeur fonction.  Cette adresse est utilisée pour exécuter la fonction.  
  
 Le module managé définit un délégué marshalé vers le code natif en tant que pointeur fonction et utilise l'attribut <xref:System.Runtime.InteropServices.DllImportAttribute> pour exposer la fonction TakesCallback native au code managé.  Dans la fonction principale, une instance du délégué est créée et passée à la fonction TakesCallback.  La sortie du programme montre que cette fonction est exécutée par la fonction TakesCallback native.  
  
 La fonction managée supprime le garbage collection du délégué managé pour empêcher le garbage collection du .NET Framework de réadresser le délégué pendant l'exécution de la fonction native.  
  
 Le module managé est compilé avec \/clr, mais \/clr:pure fonctionne également.  
  
```  
// TraditionalDll5.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   /* Declare an unmanaged function type that takes two int arguments  
      Note the use of __stdcall for compatibility with managed code */  
   typedef int (__stdcall *CALLBACK)(int);  
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);  
}  
  
int TakesCallback(CALLBACK fp, int n) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n);  
}  
```  
  
```  
// MarshalDelegate.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
public delegate int GetTheAnswerDelegate(int);  
public value struct TraditionalDLL {  
   [DllImport("TraditionalDLL5.dll")]  
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);  
};  
  
int GetNumber(int n) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
   return x + n;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TraditionalDLL::TakesCallback(fp, 42);  
}  
```  
  
 Notez qu'aucune partie de la DLL n'est exposée au code managé à l'aide de la directive \#include traditionnelle.  En réalité, l'accès à la DLL se limite au moment de l'exécution. Par conséquent, les problèmes liés aux fonctions importées à l'aide de <xref:System.Runtime.InteropServices.DllImportAttribute> ne sont pas détectés au moment de la compilation.  
  
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)