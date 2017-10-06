---
title: static_assert | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- static_assert_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ keywords, static_assert
- C2338
- assertions [C++], static_assert
- static_assert
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
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
ms.openlocfilehash: 1428d890fe079c7ac1fce175686e9776f9c21746
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="staticassert"></a>static_assert
Teste une assertion logicielle au moment de la compilation. Si l’expression constante spécifiée est `false`, le compilateur affiche le message spécifié, le cas échéant et la compilation échoue avec l’erreur C2338 ; sinon, la déclaration n’a aucun effet.  
  
## <a name="syntax"></a>Syntaxe  
  
```   
static_assert( constant-expression, string-literal );  

**Visual Studio 2017 and later:**
static_assert( constant-expression ); 
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`constant-expression`|Expression constante intégrale pouvant être convertie en expression booléenne.<br /><br /> Si l'expression évaluée a la valeur zéro (fausse), le paramètre `string-literal` s'affiche et la compilation échoue avec une erreur. Si l'expression a une valeur non nulle (vraie), la déclaration `static_assert` n'a aucun effet.|  
|`string-literal`|Message qui s'affiche si le paramètre `constant-expression` a la valeur zéro. Le message est une chaîne de caractères dans le [jeu de caractères de base](../c-language/ascii-character-set.md) du compilateur ; c'est-à-dire, pas [caractères multioctets ou larges](../c-language/multibyte-and-wide-characters.md).|  
  
## <a name="remarks"></a>Remarques  
 Le `constant-expression` paramètre d’un `static_assert` déclaration représente un *assertion logicielle*. Une assertion logicielle spécifie une condition supposée être vraie en un point particulier de votre programme. Si la condition est vraie, la déclaration `static_assert` n'a aucun effet. Si la condition est fausse, l'assertion échoue, le compilateur affiche le message dans le paramètre `string-literal` et la compilation échoue avec une erreur. Dans Visual Studio 2017 et versions ultérieures, le paramètre de littéral de chaîne est facultatif. 
  
 La déclaration `static_assert` teste une assertion logicielle au moment de la compilation. En revanche, le [assert (macro), _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) macro teste une assertion logicielle au moment de l’exécution et implique un coût d’exécution dans un espace ou d’heure. La déclaration `static_assert` est particulièrement utile pour déboguer des modèles, car des arguments template peuvent être inclus dans le paramètre `constant-expression`.  
  
 Le compilateur examine la déclaration `static_assert` pour rechercher des erreurs de syntaxe, lorsque la déclaration est rencontrée. Le compilateur évalue immédiatement le paramètre `constant-expression` s'il ne dépend pas d'un paramètre de modèle. Sinon, le compilateur évalue le paramètre `constant-expression` lorsque le modèle est instancié. Par conséquent, le compilateur peut publier un message de diagnostic une fois la déclaration rencontrée, puis à nouveau lorsque le modèle est instancié.  
  
 Vous pouvez utiliser le mot clé `static_assert` au niveau de la portée espace de noms, de classe ou de bloc. (Techniquement, le mot clé `static_assert` est une déclaration, même s'il ne présente pas de nouveau nom dans votre programme, car il peut être utilisé au niveau de la portée espace de noms.)  
  
## <a name="description"></a>Description  
 Dans l'exemple ci-dessous, la déclaration `static_assert` a une portée espace de nom. Comme le compilateur connaît la taille du type `void *`, l'expression est évaluée immédiatement.  
  
## <a name="example"></a>Exemple  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## <a name="description"></a>Description  
 Dans l'exemple ci-dessous, la déclaration `static_assert` a une portée de classe. Le `static_assert` vérifie qu’un paramètre de modèle est un *données* type (POD). Le compilateur examine la déclaration `static_assert` lorsqu'elle est déclarée, mais n'évalue pas le paramètre `constant-expression` tant que le modèle de classe `basic_string` n'a pas été instancié dans `main()`.  
  
## <a name="example"></a>Exemple  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(std::is_pod<CharT>::value,  
                  "Template argument CharT must be a POD type in class template basic_string");  
    // ...  
    };  
}  
  
struct NonPOD {  
    NonPOD(const NonPOD &) {}  
    virtual ~NonPOD() {}  
};  
  
int main()  
{  
    std::basic_string<char> bs;  
}  
```  
  
## <a name="description"></a>Description  
 Dans l'exemple ci-dessous, la déclaration `static_assert` a une portée de bloc. `static_assert` vérifie que la taille de la structure VMPage est égale à la taille de page de mémoire virtuelle du système.  
  
## <a name="example"></a>Exemple  
  
```  
#include <sys/param.h> // defines PAGESIZE  
class VMMClient {  
public:  
    struct VMPage { // ...   
           };  
    int check_pagesize() {  
    static_assert(sizeof(VMPage) == PAGESIZE,  
        "Struct VMPage must be the same size as a system virtual memory page.");  
    // ...  
    }  
// ...  
};  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Assertion et Messages fournis par l’utilisateur (C++)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [#error (directive) (C/C++)](../preprocessor/hash-error-directive-c-cpp.md)   
 [Macro assert, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Modèles](../cpp/templates-cpp.md)   
 [Jeu de caractères ASCII](../c-language/ascii-character-set.md)   
 [Déclarations et définitions](declarations-and-definitions-cpp.md)
