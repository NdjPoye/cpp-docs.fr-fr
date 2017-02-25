---
title: "Comment&#160;: marshaler des cha&#238;nes &#224; l&#39;aide de PInvoke | Microsoft Docs"
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
  - "marshaling de données (C++), chaînes"
  - "Interop (C++), chaînes"
  - "marshaling (C++), chaînes"
  - "appel de code non managé (C++), chaînes"
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Comment&#160;: marshaler des cha&#238;nes &#224; l&#39;aide de PInvoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment les fonctions natives qui acceptent des chaînes de style C peuvent être appelées à l'aide du System::String de type de chaîne du CLR grâce à la prise en charge de l'appel de code non managé .NET Framework.  Les programmeurs Visual C\+\+ sont encouragés à utiliser plutôt les fonctionnalités d'interopérabilité C\+\+ \(dans la mesure du possible\), car P\/Invoke ne signale pas correctement les erreurs de compilation, n'est pas de type sécurisé et peut être fastidieux à implémenter.  Si l'API non managée se présente sous la forme d'une DLL et si le code source n'est pas disponible, P\/Invoke est votre seule option \(sinon, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)\).  
  
 Les chaînes managées et non managées sont disposées différemment en mémoire ; par conséquent, le passage de chaînes de fonctions managées vers des fonctions non managées exige l'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> pour indiquer au compilateur d'insérer les mécanismes de conversion requis pour marshaler les données de type chaîne correctement et sans risque.  
  
 Comme pour les fonctions qui utilisent uniquement des types de données intrinsèques, <xref:System.Runtime.InteropServices.DllImportAttribute> est utilisé pour déclarer des points d'entrée managés dans les fonctions natives mais, pour passer des chaînes, un handle du type <xref:System.String> peut être utilisé plutôt que de définir ces points d'entrée comme prenant des chaînes de style C.  Le compilateur est ainsi invité à insérer le code qui exécute la conversion requise.  Pour chaque argument de fonction contenu dans une fonction non managée prenant une chaîne, l'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> doit être utilisé pour indiquer que l'objet String doit être marshalé vers la fonction native en tant que chaîne de style C.  
  
## Exemple  
 Le code suivant est constitué d'un module non managé et d'un module managé.  Le module non managé est une DLL définissant une fonction appelée TakesAString qui accepte une chaîne ANSI de style C sous la forme d'un char\*.  Le module managé est une application en ligne de commande qui importe la fonction TakesAString, mais la définit comme prenant un System.String managé plutôt qu'un char\*.  L'attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute> est utilisé pour indiquer de quelle manière la chaîne managée doit être marshalée lors d'un appel à TakesAString.  
  
 Le module managé est compilé avec \/clr, mais \/clr:pure fonctionne également.  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 Cette technique entraîne la création d'une copie de la chaîne sur le tas non managé ; par conséquent, les modifications apportées à la chaîne par la fonction native ne sont pas répercutées dans la copie managée de la chaîne.  
  
 Notez qu'aucune partie de la DLL n'est exposée au code managé à l'aide de la directive \#include traditionnelle.  En réalité, l'accès à la DLL est limité au moment de l'exécution. Par conséquent, les problèmes liés aux fonctions importées à l'aide de `DllImport` ne sont pas détectés au moment de la compilation.  
  
## Voir aussi  
 [Utilisation d'un PInvoke explicite en C\+\+ \(attribut DllImport\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)