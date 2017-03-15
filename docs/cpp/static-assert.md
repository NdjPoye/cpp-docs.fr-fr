---
title: "static_assert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "C2338"
  - "static_assert_cpp"
  - "static_assert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assertions (C++), static_assert"
  - "mots clés C++, static_assert"
  - "C2338"
  - "static_assert"
ms.assetid: 28dd3668-e78c-4de8-ba68-552084743426
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# static_assert
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Teste une assertion logicielle au moment de la compilation.  Si l'expression constante spécifiée présente la valeur `false`, le compilateur affiche le message spécifié et la compilation échoue avec l'erreur C2338. Sinon, la déclaration n'a aucun effet.  
  
## Syntaxe  
  
```  
static_assert(   
    constant-expression,   
    string-literal   
);  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`constant-expression`|Expression constante intégrale pouvant être convertie en expression booléenne.<br /><br /> Si l'expression évaluée a la valeur zéro \(fausse\), le paramètre `string-literal` s'affiche et la compilation échoue avec une erreur.  Si l'expression a une valeur non nulle \(vraie\), la déclaration `static_assert` n'a aucun effet.|  
|`string-literal`|Message qui s'affiche si le paramètre `constant-expression` a la valeur zéro.  Le message est une chaîne de caractères dans le [jeu de caractères de base](../c-language/ascii-character-set.md) du compilateur. Autrement dit, il n'est pas constitué de [caractères multioctets ou larges](../c-language/multibyte-and-wide-characters.md).|  
  
## Notes  
 Le paramètre `constant-expression` d'une déclaration `static_assert` représente une *assertion logicielle*.  Une assertion logicielle spécifie une condition supposée être vraie en un point particulier de votre programme.  Si la condition est vraie, la déclaration `static_assert` n'a aucun effet.  Si la condition est fausse, l'assertion échoue, le compilateur affiche le message dans le paramètre `string-literal` et la compilation échoue avec une erreur.  
  
 La déclaration `static_assert` teste une assertion logicielle au moment de la compilation.  En revanche, la macro [assert \(macro\), \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) teste une assertion logicielle au moment de l'exécution et entraîne des coûts d'exécution en termes d'espace ou de temps.  La déclaration `static_assert` est particulièrement utile pour déboguer des modèles, car des arguments template peuvent être inclus dans le paramètre `constant-expression`.  
  
 Le compilateur examine la déclaration `static_assert` pour rechercher des erreurs de syntaxe, lorsque la déclaration est rencontrée.  Le compilateur évalue immédiatement le paramètre `constant-expression` s'il ne dépend pas d'un paramètre de modèle.  Sinon, le compilateur évalue le paramètre `constant-expression` lorsque le modèle est instancié.  Par conséquent, le compilateur peut publier un message de diagnostic une fois la déclaration rencontrée, puis à nouveau lorsque le modèle est instancié.  
  
 Vous pouvez utiliser le mot clé `static_assert` au niveau de la portée espace de noms, de classe ou de bloc. \(Techniquement, le mot clé `static_assert` est une déclaration, même s'il ne présente pas de nouveau nom dans votre programme, car il peut être utilisé au niveau de la portée espace de noms.\)  
  
## Description  
 Dans l'exemple ci\-dessous, la déclaration `static_assert` a une portée espace de nom.  Comme le compilateur connaît la taille du type `void *`, l'expression est évaluée immédiatement.  
  
## Exemple  
  
```  
static_assert(sizeof(void *) == 4, "64-bit code generation is not supported.");  
```  
  
## Description  
 Dans l'exemple ci\-dessous, la déclaration `static_assert` a une portée de classe.  `static_assert` vérifie qu'un paramètre de modèle est de type traditionnel *POD* \(Plain Old Data\).  Le compilateur examine la déclaration `static_assert` lorsqu'elle est déclarée, mais n'évalue pas le paramètre `constant-expression` tant que le modèle de classe `basic_string` n'a pas été instancié dans `main()`.  
  
## Exemple  
  
```  
#include <type_traits>  
#include <iosfwd>  
namespace std {  
template <class CharT, class Traits = std::char_traits<CharT> >  
class basic_string {  
    static_assert(tr1::is_pod<CharT>::value,  
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
  
## Description  
 Dans l'exemple ci\-dessous, la déclaration `static_assert` a une portée de bloc.  `static_assert` vérifie que la taille de la structure VMPage est égale à la taille de page de mémoire virtuelle du système.  
  
## Exemple  
  
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
  
## Voir aussi  
 [Assertion et messages fournis par l'utilisateur \(C\+\+\)](../cpp/assertion-and-user-supplied-messages-cpp.md)   
 [\#error, directive](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert \(macro\), \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [Modèles](../cpp/templates-cpp.md)   
 [Jeu de caractères ASCII](../c-language/ascii-character-set.md)   
 [Déclarations](../misc/declarations.md)