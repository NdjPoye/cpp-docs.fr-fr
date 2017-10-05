---
title: Comportement non standard | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 13420db99afa801d02306f4dd8af4104ec322bd5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="nonstandard-behavior"></a>Comportement non standard
Les sections suivantes répertorient certaines des situations dans lesquelles l'implémentation Visual C++ n'est pas conforme à la norme C++. Les numéros de section ci-dessous correspondent aux numéros de section de la norme C++11 (ISO/IEC 14882:2011(E)).  
  
 Donne la liste des limites du compilateur qui diffèrent de ceux définis dans la norme C++ [limites du compilateur](../cpp/compiler-limits.md).  
  
## <a name="covariant-return-types"></a>Types de retour covariant  
 Les classes de base virtuelle ne sont pas prises en charge en tant que types de retour covariants lorsque la fonction virtuelle a un nombre d'arguments variable. Ceci n'est pas conforme à la section 10.3, paragraphe 7 de la spécification ISO C++. L’exemple suivant ne se compile pas, donnant l’erreur du compilateur [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)  
  
```cpp  
// CovariantReturn.cpp  
class A   
{  
   virtual A* f(int c, ...);   // remove ...  
};  
  
class B : virtual A  
{  
   B* f(int c, ...);   // C2688 remove ...  
};  
```  
  
## <a name="binding-nondependent-names-in-templates"></a>Liaison de noms non dépendants dans des modèles  
 Le compilateur Visual C++ ne prend pas en charge actuellement la liaison des noms non dépendants lors de l'analyse initiale d'un modèle. Ceci n'est pas conforme à la section 14.6.3 de la spécification ISO C++. Cela peut provoquer la déclaration de surcharges après le modèle à afficher (mais avant que le modèle soit instancié).  
  
```cpp  
#include <iostream>  
using namespace std;  
  
namespace N {  
   void f(int) { cout << "f(int)" << endl;}  
}  
  
template <class T> void g(T) {  
    N::f('a');   // calls f(char), should call f(int)  
}  
  
namespace N {  
    void f(char) { cout << "f(char)" << endl;}  
}  
  
int main() {  
    g('c');  
}  
// Output: f(char)  
  
```  
  
## <a name="function-exception-specifiers"></a>Spécificateurs d'exceptions de fonctions  
 Les spécificateurs d'exceptions de fonction autres que `throw()` sont analysés, mais pas utilisés. Ceci n'est pas conforme à la section 15.4 de la spécification ISO C++. Exemple :  
  
```cpp  
void f() throw(int); // parsed but not used  
void g() throw();    // parsed and used  
```  
  
 Pour plus d’informations sur les spécifications d’exceptions, consultez [les spécifications d’exceptions](../cpp/exception-specifications-throw-cpp.md).  
  
## <a name="chartraitseof"></a>char_traits::eof()  
 La norme C++ [char_traits::eof](../standard-library/char-traits-struct.md#eof) ne doit pas correspondre à un serveur valide `char_type` valeur. Le compilateur Visual C++ applique cette contrainte pour le type `char`, mais pas pour le type `wchar_t`. Ceci n'est pas conforme à la spécification du tableau 62 de la section 12.1.1 de la spécification ISO C++. C'est ce qu'illustre l'exemple ci-dessous.  
  
```cpp  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    char_traits<char>::int_type int2 = char_traits<char>::eof();  
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;  
  
    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();  
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;  
}  
```  
  
## <a name="storage-location-of-objects"></a>Emplacement de stockage des objets  
 La norme C++ (section 1.8, paragraphe 6) exige que les objets C++ complets aient des emplacements de stockage uniques. Toutefois, avec Visual C++, il existe certaines situations dans lesquelles des types sans données membres partagent un emplacement de stockage avec d'autres types pendant la durée de vie de l'objet.
