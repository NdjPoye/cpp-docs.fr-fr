---
title: "Avertissement du compilateur (niveau 2) C4412 | Microsoft Docs"
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
  - "C4412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4412"
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 2) C4412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la signature de fonction contient le type 'type' ; le passage d'objets C\+\+ n'est pas sécurisé entre le code pure et le code mixte ou natif.  
  
 Le compilateur a détecté une situation potentiellement dangereuse susceptible d'entraîner une erreur d'exécution : un appel est actuellement effectué à partir d'un module \(compiland\) **\/clr:pure** à une fonction qui a été importée via dllimport et la signature de la fonction contient un type non sécurisé.  Un type n'est pas sécurisé s'il contient une fonction membre ou une donnée membre qui est un type non sécurisé ou une indirection à un type non sécurisé.  
  
 Cela est potentiellement dangereux en raison de la différence dans les conventions d'appel par défaut entre le code pur et le code natif \(ou mixte natif et managé\).  Lors de l'importation \(via `dllimport`\) d'une fonction dans un module \(compiland\) **\/clr:pure**, vérifiez que les déclarations de chaque type contenues dans la signature sont identiques à celles du module qui exporte la fonction \(soyez particulièrement vigilent en ce qui concerne les différences dans les conventions d'appel implicites\).  
  
 Une fonction membre virtuelle est particulièrement susceptible de produire des résultats inattendus.  Toutefois, même une fonction non virtuelle doit être testée pour garantir que vous obtiendrez des résultats corrects.  Si vous êtes certains d'obtenir des résultats adéquats, vous pouvez ignorer cet avertissement.  
  
 Pour plus d'informations sur **\/clr:pure**, consultez [Comment : effectuer une migration vers \/clr:pure](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 L'erreur C4412 est désactivée par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) et [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
 Pour résoudre cet avertissement, supprimez toutes les fonctions du type.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4412 :  
  
```  
// C4412.cpp  
// compile with: /c /W2 /clr:pure  
#pragma warning (default : 4412)  
  
struct Unsafe {  
   virtual void __cdecl Test();  
};  
  
struct Safe {  
   int i;  
};  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   Unsafe *pUnsafe = func();   // C4412  
   // pUnsafe->Test();  
  
   Safe *pSafe = func2();   // OK  
}  
```  
  
## Exemple  
 L'exemple suivant est un fichier d'en\-tête qui déclare deux types.  Le type `Unsafe` n'est pas sûr, car il possède une fonction membre.  
  
```  
// C4412.h  
struct Unsafe {  
   // will be __clrcall if #included in pure compilation  
   // defaults to __cdecl in native or mixed mode compilation  
   virtual void Test(int * pi);  
  
   // try the following line instead  
   // virtual void __cdecl Test(int * pi);  
};  
  
struct Safe {  
   int i;  
};  
```  
  
## Exemple  
 Cet exemple exporte des fonctions avec les types définis dans le fichier d'en\-tête.  
  
```  
// C4412_2.cpp  
// compile with: /LD  
#include "C4412.h"  
  
void Unsafe::Test(int * pi) {  
   *pi++;  
}  
  
__declspec(dllexport) Unsafe * __cdecl func() { return new Unsafe; }  
__declspec(dllexport) Safe * __cdecl func2() { return new Safe; }  
```  
  
## Exemple  
 La convention d'appel par défaut contenue dans une compilation **\/clr:pure** est différente d'une compilation native.  Lorsque C4412.h est inclus, `Test` a par défaut la valeur `__clrcall`.  Si vous compilez et exécutez ce programme \(sans utiliser **\/c**\), le programme lève une exception.  
  
 L'exemple suivant génère l'erreur C4412 :  
  
```  
// C4412_3.cpp  
// compile with: /W2 /clr:pure /c /link C4412_2.lib  
#pragma warning (default : 4412)  
#include "C4412.h"  
  
__declspec(dllimport) Unsafe * __cdecl func();  
__declspec(dllimport) Safe * __cdecl func2();  
  
int main() {  
   int n = 7;  
   Unsafe *pUnsafe = func();   // C4412  
   pUnsafe->Test(&n);  
  
   Safe *pSafe = func2();   // OK  
}  
```