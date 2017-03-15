---
title: Erreur du compilateur C2065 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2065
dev_langs:
- C++
helpviewer_keywords:
- C2065
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 81686df4727ab2b3d5af749174a42016e8443e70
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2065"></a>Erreur du compilateur C2065
'identificateur' : identificateur non déclaré  
  
 Le type d'une variable doit être spécifié dans une déclaration avant de pouvoir être utilisé. Les paramètres utilisés par une fonction doivent être spécifiés dans une déclaration ou un prototype pour que la fonction puisse être utilisée.  
  
 Causes possibles :  
  
1.  Le nom de l'identificateur est mal orthographié.  
  
2.  L'identificateur utilise une combinaison erronée de majuscules et minuscules.  
  
3.  Les guillemets de fermeture sont manquants après une constante de chaîne.  
  
4.  Vous compilez avec une version de débogage du runtime C, déclarez une variable d’itérateur de bibliothèque C++ Standard dans une `for` une boucle, puis essayez d’utiliser cette variable d’itérateur en dehors de l’étendue de la `for` boucle. La compilation du code de bibliothèque C++ Standard avec une version de débogage du runtime C implique [/Zc : forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  Consultez la page [prise en charge itérateur débogage](../../standard-library/debug-iterator-support.md) pour plus d’informations.  
  
5.  Vous appelez peut-être une fonction dans un fichier d'en-tête SDK qui n'est actuellement pas prise en charge dans votre environnement de génération.  
  
6.  Omission de fichiers Include nécessaires, en particulier si vous définissez `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` ou `WIN32_EXTRA_LEAN`. Ces symboles excluent certains fichiers d'en-tête de windows.h et afxv_w32.h pour accélérer les compilations. (Recherchez dans windows.h et afxv_w32.h une description à jour de ce qui est exclu.)  
  
7.  Portée espace de noms incorrecte. Par exemple, pour résoudre les fonctions et les opérateurs de la bibliothèque standard C++ qui ne sont pas entièrement qualifiés, vous devez spécifier l'espace de noms `std` avec la directive `using`. Dans l'exemple suivant, la compilation échoue car la directive `using` est commentée et que `cout` est défini dans l'espace de noms `std` :  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## <a name="example"></a>Exemple  
 Lorsque vous appelez une fonction générique, si l’argument de type prévu ne peut pas être déduit des paramètres utilisés, le compilateur signale une erreur. Pour plus d’informations, consultez [fonctions génériques (C + c++ / CLI)](../../windows/generic-functions-cpp-cli.md).  
  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## <a name="example"></a>Exemple  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual C++ 2005 : vérification des paramètres des attributs Visual C++.  
  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```
