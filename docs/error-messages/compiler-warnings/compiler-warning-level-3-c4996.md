---
title: Compilateur avertissement (niveau 3) C4996 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 4a82bbdd3b28ae0150ab8366d3ecbe849e7ac8a1
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4996"></a>Compilateur avertissement (niveau 3) C4996
Le compilateur a rencontré une déclaration déconseillée.  
  
 Cet avertissement ou cette erreur a plusieurs significations possibles.  
  
 `C4996`se produit lorsque le compilateur rencontre une fonction ou une variable qui est marqué comme étant [déconseillée](../../cpp/deprecated-cpp.md). Plusieurs fonctions, des fonctions membres, des fonctions de modèle et des variables globales des bibliothèques de Visual Studio sont marquées comme déconseillées. Ces fonctions peuvent avoir un autre nom préféré, peuvent être risquées ou avoir une variante plus sécurisée, ou bien être obsolètes. Le message d’erreur peut inclure une suggestion de remplacement pour la fonction ou la variable globale déconseillée. Vous pouvez désactiver cet avertissement avec le [avertissement](../../preprocessor/warning.md) pragma ou **/wd4996** l’option de ligne de commande. Vous pouvez également utiliser des macros de préprocesseur pour désactiver certaines classes d’avertissements concernant les éléments déconseillés. 

Cet avertissement est également émis lorsque vous tentez d’accéder à une fonction, un membre de classe ou un typedef qui a C ++ 14 `[[deprecated]]` attribut. Pour plus d’informations, consultez [attributs Standard C++](../../cpp/attributes2.md). 
  
 **Le nom POSIX pour cet élément est déconseillé. Au lieu de cela, utilisez le nom conforme ISO C et C++ :** nouveau_nom**. Consultez l’aide en ligne pour plus d’informations.**  
  
 Certaines fonctions POSIX de la bibliothèque CRT ont été renommées pour les rendre conformes aux règles C99 et C++03 quant aux noms de fonctions globaux définis par l’implémentation. Dans la plupart des cas, un trait de soulignement de début a été ajouté au nom de fonction POSIX pour créer un nom conforme à la norme. Le compilateur émet un avertissement indiquant que les noms d’origine des fonctions sont déconseillés et suggère le nom préféré. Seuls les noms d’origine sont déconseillés, mais pas les fonctions elles-mêmes. Pour désactiver les avertissements déconseillant ces fonctions, définissez la macro de préprocesseur **_CRT_NONSTDC_NO_WARNINGS**. Vous pouvez la définir sur la ligne de commande en incluant l’option `/D_CRT_NONSTDC_NO_WARNINGS`. Pour définir cette macro dans Visual Studio, ouvrez la boîte de dialogue **Pages de propriétés** pour votre projet. Développez **Propriétés de configuration**, **C/C++**, **Préprocesseur**. Dans **Définitions de préprocesseur**, ajoutez `_CRT_NONSTDC_NO_WARNINGS`. Choisissez **OK** pour enregistrer, puis régénérez votre projet. Pour définir cette macro seulement dans des fichiers sources spécifiques, ajoutez la ligne `#define _CRT_NONSTDC_NO_WARNINGS` avant une ligne incluant un fichier d’en-tête.  
  
 **Cette fonction ou une variable peut être dangereux. Envisagez d’utiliser** version_sécurisée **à la place. Pour désactiver le message déconseillant l’utilisation, utilisez _CRT_SECURE_NO_WARNINGS.  Consultez l’aide en ligne pour plus d’informations.**  
  
 Certaines fonctions CRT et la bibliothèque C++ Standard et les variables globales ont été déconseillées en faveur de nouvelles fonctions, plus sécurisées. Le compilateur émet un avertissement indiquant que ces fonctions sont déconseillées et suggère la fonction préférée. Pour désactiver les avertissements déconseillant ces fonctions dans la bibliothèque CRT, définissez **_CRT_SECURE_NO_WARNINGS**. Pour désactiver les avertissements relatifs à des variables globales déconseillées, définissez **_CRT_SECURE_NO_WARNINGS_GLOBALS**. Pour plus d’informations sur ces fonctions déconseillées et les variables globales, consultez [les fonctionnalités de sécurité dans la bibliothèque CRT](../../c-runtime-library/security-features-in-the-crt.md) et [bibliothèques sécurisées : bibliothèque Standard C++](../../standard-library/safe-libraries-cpp-standard-library.md).  
  
 **Appel de fonction avec des paramètres qui peuvent être non sécurisés : cet appel s’appuie sur l’appelant pour vérifier que les valeurs passées sont corrects. Pour désactiver cet avertissement, utilisez -D_SCL_SECURE_NO_WARNINGS. Consultez la documentation sur l’utilisation des « Itérateurs vérifiés » Visual C++**  
  
 Certaines fonctions de modèle de la bibliothèque C++ standard ne vérifient pas que les paramètres sont corrects. Cet avertissement vous permet d’identifier l’utilisation de ces fonctions. Pour désactiver les avertissements pour ces fonctions, définissez **_SCL_SECURE_NO_WARNINGS**. Pour plus d’informations, consultez [Itérateurs vérifiés](../../standard-library/checked-iterators.md).  
  
 **Cette fonction ou une variable a été remplacée par la fonctionnalité de bibliothèque ou un système d’exploitation plus récente. Envisagez d’utiliser** Nouvel_élément **à la place. Consultez l’aide en ligne pour plus d’informations.**  
  
 Certaines fonctions de la bibliothèque et certaines variables globales sont déconseillées, car elles sont obsolètes. Ces fonctions et variables sont susceptibles d’être supprimées dans une version future de la bibliothèque. Le compilateur émet un avertissement indiquant que ces éléments sont déconseillées et suggère l’alternative préférée. Pour désactiver les avertissements déconseillant ces éléments, définissez **_CRT_OBSOLETE_NO_WARNINGS**. Pour plus d’informations, consultez la documentation pour la fonction ou la variable déconseillée.  
  
 **Différents messages dans le code MFC ou ATL**  
  
 L'erreur `C4996` peut également se produire si vous utilisez des fonctions MFC ou ATL qui ont été déconseillées pour des raisons de sécurité. Pour supprimer ces avertissements, consultez [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings) et [_ATL_SECURE_NO_WARNINGS](http://msdn.microsoft.com/Library/587d29d8-a75a-44a3-bec8-f724087e5e73).  
  
 **Marshaling des erreurs dans le code CLR**  
  
 L'erreur `C4996` peut également se produire lorsque vous utilisez la bibliothèque de marshaling. Dans ce cas, C4996 est une erreur, plutôt qu'un avertissement. Cette erreur se produit lorsque vous utilisez [marshal_as](../../dotnet/marshal-as.md) pour effectuer une conversion entre deux types de données qui nécessitent une [marshal_context, classe](../../dotnet/marshal-context-class.md). Vous recevez également cette erreur lorsque la bibliothèque de marshaling ne prend pas de conversion en charge. Pour plus d’informations sur la bibliothèque de marshaling, consultez [vue d’ensemble du Marshaling dans C++](../../dotnet/overview-of-marshaling-in-cpp.md).  
  
 **Exemples qui génèrent l’erreur C4996**  
  
 Dans le premier exemple, `C4996` est généré pour la ligne dans laquelle la fonction est déclarée et pour la ligne dans laquelle la fonction est utilisée.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4996.  
  
```cpp  
// C4996.cpp  
// compile with: /W3  
// C4996 warning expected  
#include <stdio.h>  
  
// #pragma warning(disable : 4996)  
void func1(void) {  
   printf_s("\nIn func1");  
}  
  
__declspec(deprecated) void func1(int) {  
   printf_s("\nIn func2");  
}  
  
int main() {  
   func1();  
   func1(1);  
}  
```  
  
## <a name="example"></a>Exemple  
 Le message C4996 peut également s'afficher si vous n'utilisez pas d'itérateur vérifié lors de la compilation quand `_ITERATOR_DEBUG_LEVEL` est défini (défini à 1 par défaut pour les builds en mode débogage).  Pour plus d’informations, voir [Itérateurs vérifiés](../../standard-library/checked-iterators.md).  
  
 L’exemple de code de bibliothèque Standard C++ suivant génère l’erreur C4996.  
  
```cpp  
// C4996_b.cpp  
// compile with: /EHsc /W3 /c  
#define _ITERATOR_DEBUG_LEVEL 1  
  
#include <algorithm>  
#include <iterator>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
    int a[] = { 1, 2, 3 };  
    int b[] = { 10, 11, 12 };  
    copy(a, a + 3, b + 1);   // C4996  
    // try the following line instead  
    //   copy(a, a + 3, b);  
    copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK  
}  
  
```  
  
## <a name="example"></a>Exemple  
 L’exemple de code de bibliothèque Standard C++ suivant génère l’erreur C4996 en tant qu’avertissement. Les commentaires sont inline.  
  
```cpp  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to C++ Standard Library algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (i.e. an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (i.e. it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère le message C4996, car la bibliothèque de marshaling a besoin d'un contexte pour effectuer une conversion de `System::String` en `const char *`.  
  
```cpp  
// C4996_Marshal.cpp  
// compile with: /clr   
// C4996 expected  
#include <stdlib.h>  
#include <string.h>  
#include <msclr\marshal.h>  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   String^ message = gcnew String("Test String to Marshal");  
   const char* result;  
   result = marshal_as<const char*>( message );  
   return 0;  
}  
```

