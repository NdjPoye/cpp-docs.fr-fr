---
title: Compilateur avertissement (niveau 2) C4412 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4412
dev_langs:
- C++
helpviewer_keywords:
- C4412
ms.assetid: f28dc531-1a98-497b-a366-0a13e1bc81c7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 92aa12514088d0fbffbe826a495d76b49ab311d1
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-2-c4412"></a>Avertissement du compilateur (niveau 2) C4412
'fonction' : signature de fonction contient le type 'type' ; Objets C++ sont unsafe à passer entre le code pure et mixte ou natif.  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Le compilateur a détecté une situation potentiellement dangereuse qui risque d’entraîner une erreur d’exécution : un appel est effectué dans un **/CLR : pure** compiland à une fonction qui a été importée via dllimport et la signature de fonction contienne un type non sécurisé. Un type est unsafe s’il contient une fonction membre ou une donnée membre qui est un type non sécurisé ou une indirection à un type non sécurisé.  
  
 Cela n’est pas sûre en raison de la différence entre la valeur par défaut conventions entre le code pure et native d’appel (ou mixte natif et managé). Lors de l’importation (via `dllimport`) une fonction dans une **/CLR : pure** compiland, assurez-vous que les déclarations de chaque type dans la signature sont identiques à celles du module qui exporte la fonction (veillant particulièrement sur les différences dans les conventions d’appel implicites).  
  
 Une fonction membre virtuelle est particulièrement susceptible de produire des résultats inattendus.  Toutefois, même une fonction non virtuelle doit être testée pour vous assurer d’obtenir les résultats corrects. Si vous êtes sûr que vous obtenez les résultats corrects, vous pouvez ignorer cet avertissement.  
  
 Pour plus d’informations sur **/CLR : pure**, consultez [Comment : migrer vers/clr : pure (C + c++ / CLI)](../../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md).  
  
 L’erreur C4412 est désactivée par défaut. Consultez la page [les avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) et [dllexport, dllimport](../../cpp/dllexport-dllimport.md) pour plus d’informations.  
  
 Pour résoudre cet avertissement, supprimez toutes les fonctions du type.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4412.  
  
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
  
## <a name="example"></a>Exemple  
 L’exemple suivant est un fichier d’en-tête qui déclare deux types. Le `Unsafe` type est dangereux, car il contient une fonction membre.  
  
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
  
## <a name="example"></a>Exemple  
 Cet exemple exporte des fonctions avec les types définis dans le fichier d’en-tête.  
  
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
  
## <a name="example"></a>Exemple  
 La valeur par défaut de convention d’appel un **/CLR : pure** compilation est différente d’une compilation native.  Lorsque C4412.h est inclus, `Test` par défaut est `__clrcall`. Si vous compilez et exécutez ce programme (n’utilisez pas **/c**), le programme lève une exception.  
  
 L’exemple suivant génère l’erreur C4412.  
  
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
