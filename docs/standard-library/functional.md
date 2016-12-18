---
title: "&lt; fonctionnel &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<functional>"
  - "functional/std::<functional>"
  - "std.<functional>"
  - "std::<functional>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "foncteurs"
  - "functional (en-tête)"
ms.assetid: 7dd463e8-a29f-49bc-aedd-8fa53b54bfbc
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; fonctionnel &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les fonctions de bibliothèque Standard qui permettent de construire *objets de fonction*également appelé functors — et leurs classeurs. Un objet de fonction est un objet d'un type qui définit `operator()`. Un objet de fonction peut être un pointeur fonction, mais en général il sert à stocker des informations supplémentaires accessibles pendant un appel de fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <functional>  
```  
  
## <a name="remarks"></a>Remarques  
 Les algorithmes nécessitent deux types d'objets de fonction : unaire et binaire. Les objets de fonction unaires nécessitent un argument et les objets de fonction binaires nécessitent deux arguments. Un objet de fonction et des pointeurs fonction peuvent être passés en tant que prédicat à un algorithme, mais les objets de fonction sont également adaptables et augmentent la portée, la flexibilité et l'efficacité de la bibliothèque STL. Si, par exemple, une valeur doit être liée à une fonction avant d'être passée à un algorithme, vous ne pouvez pas utiliser un pointeur fonction. Les adaptateurs de fonction convertissent des pointeurs fonction en objets de fonction adaptables qui peuvent être liés à une valeur. L’en-tête \< fonctionnel> contient également des adaptateurs de fonction membre qui permettent des fonctions d’être appelées en tant qu’objets de fonction adaptables membre. Les fonctions sont adaptables si elles ont des déclarations de type imbriquées spécifiant leur argument et leurs types de retour. La norme C++ impose que cette capacité d'adaptation soit implémentée en faisant en sorte que toutes les classes d'objets standard héritent des classes de base unary_function ou binary_function. Les objets de fonction et leurs adaptateurs permettent à la bibliothèque STL de mettre à niveau les applications existantes et aident à intégrer la bibliothèque STL dans l'environnement de programmation C++.  
  
 Le [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] implémentation des objets de fonction \< fonctionnel> inclut *foncteurs*, qui sont des spécialisations de la norme objets de fonction et n’accepter aucun paramètre de modèle et d’effectuer le transfert parfait des arguments de fonction et parfait retour du résultat. Cette fonctionnalité fait partie de la spécification C++14 Draft Standard. Ces spécialisations de modèle ne vous obligent pas à spécifier des types d'arguments quand vous appelez des foncteurs d'opérateurs arithmétiques, de comparaison, logiques et au niveau du bit. Vous pouvez surcharger des opérateurs arithmétiques, de comparaison, logiques ou au niveau du bit pour vos propres types, ou pour des combinaisons hétérogènes de types, puis utiliser les foncteurs d’opérateurs transparents en tant qu’arguments de fonction. Par exemple, si votre type *MyType* implémente `operator<`, vous pouvez appeler `sort(my_collection.begin(), my_collection.end(), less<>())` au lieu de spécifier explicitement le type `sort(my_collection.begin(), my_collection.end(), less<MyType>())`.  
  
## <a name="c11c14-implementation"></a>Implémentation C++11/C++14  
 Les fonctionnalités suivantes sont ajoutées dans l’implémentation Visual C++ de C++11/C++14 :  
  
-   Un *signature d’appel* est le nom d’un type de retour suivi d’une liste séparée par des virgules entre parenthèses zéro ou plusieurs des types d’arguments.  
  
-   Un *peut être appelé type* est un pointeur fonction, un pointeur vers une fonction membre, un pointeur vers des données membres, ou un type de classe dont les objets peuvent apparaître immédiatement à gauche d’un opérateur d’appel de fonction.  
  
-   Un *peut être appelé objet* est un objet d’un type peut être appelé.  
  
-   Un *type de wrapper d’appel* est un type qui conserve un objet pouvant être appelé et prend en charge une opération d’appel qui transfère à cet objet.  
  
-   Un *enveloppe d’appel* est un objet d’un type de wrapper d’appel.  
  
-   Un *objet cible* est l’objet peut être appelé détenue par un objet de wrapper d’appel.  
  
 La pseudo-fonction `INVOKE(f, t1, t2, ..., tN)` signifie l'une des choses suivantes :  
  
- `(t1.*f)(t2, ..., tN)` quand `f` est un pointeur vers une fonction membre de classe `T` et `t1` est un objet de type `T` ou une référence à un objet de type `T` ou une référence à un objet d'un type dérivé de `T`.  
  
- `((*t1).*f)(t2, ..., tN)` quand `f` est un pointeur vers une fonction membre de classe `T` et `t1` n'est pas l'un des types décrits dans l'élément précédent.  
  
- `t1.*f` quand N == 1 et `f` est un pointeur vers des données de membre d'une classe `T` et `t1` est un objet de type `T` ou une référence à un objet de type `T` ou une référence à un objet d'un type dérivé de `T`.  
  
- `(*t1).*f` quand N == 1 et `f` est un pointeur vers des données de membre d'une classe `T` et `t1` n'est pas l'un des types décrits dans l'élément précédent.  
  
- `f(t1, t2, ..., tN)` dans tous les autres cas.  
  
 La pseudo-fonction `INVOKE(f, t1, t2, ..., tN, R)` signifie `INVOKE(f, t1, t2, ..., tN)` implicitement converti en `R`.  
  
 Si un appel wrapper a un *type de résultat faible*, le type de son type de membre `result_type` est basé sur le type de `T` de l’objet cible du wrapper, comme suit :  
  
-   Si `T` est un pointeur vers une fonction, `result_type` est un synonyme du type de retour de `T`.  
  
-   Si `T` est un pointeur vers une fonction membre, `result_type` est un synonyme du type de retour de `T`.  
  
-   Si `T` est un type de classe qui a un type de membre `result_type`, `result_type` est un synonyme de `T::result_type`.  
  
-   Sinon, il n'existe aucun membre `result_type`.  
  
 Chaque wrapper d'appel a un constructeur de déplacement et un constructeur de copie. Un *simple appel wrapper* est un wrapper d’appel qui a une assignation opérateur et dont le constructeur de copie, le constructeur de déplacement et l’opérateur d’assignation ne lève pas d’exceptions. Un *transfert de wrapper d’appel* est un wrapper d’appel qui peut être appelé à l’aide d’une liste d’arguments arbitraires et qui fournit les arguments à l’objet peut être appelé encapsulé en tant que références. Tous les arguments rvalue sont remis en tant que références rvalue et les arguments lvalue sont remis en tant que références lvalue.  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[bad_function_call](../standard-library/bad-function-call-class.md)|Une classe qui décrit une exception levée pour indiquer qu’un appel à `operator()` sur un [fonction](../standard-library/function-class.md) objet a échoué car l’objet est vide.|  
|[binary_negate](../standard-library/binary-negate-class.md)|Classe de modèle fournissant une fonction membre qui inverse la valeur de retour d'une fonction binaire spécifiée.|  
|[binder1st](../standard-library/binder1st-class.md)|Classe de modèle fournissant un constructeur qui convertit un objet de fonction binaire en objet de fonction unaire en liant le premier argument de la fonction binaire à une valeur spécifiée.|  
|[binder2nd](../standard-library/binder2nd-class.md)|Classe de modèle fournissant un constructeur qui convertit un objet de fonction binaire en objet de fonction unaire en liant le second argument de la fonction binaire à une valeur spécifiée.|  
|[const_mem_fun_ref_t](../standard-library/const-mem-fun-ref-t-class.md)|Classe d’adaptateur qui permet à une fonction membre const qui n’accepte aucun argument d’être appelée comme objet de fonction unaire en cas d’initialisation avec un argument de référence.|  
|[const_mem_fun_t](../standard-library/const-mem-fun-t-class.md)|Classe d’adaptateur qui permet à une fonction membre const qui n’accepte aucun argument d’être appelée comme objet de fonction unaire en cas d’initialisation avec un argument de pointeur.|  
|[const_mem_fun1_ref_t](../standard-library/const-mem-fun1-ref-t-class.md)|Classe d’adaptateur qui permet à une fonction membre const qui accepte un seul argument d’être appelée comme objet de fonction binaire en cas d’initialisation avec un argument de référence.|  
|[const_mem_fun1_t](../standard-library/const-mem-fun1-t-class.md)|Classe d’adaptateur qui permet à une fonction membre const qui accepte un seul argument d’être appelée comme objet de fonction binaire en cas d’initialisation avec un argument de pointeur.|  
|[(fonction)](../standard-library/function-class.md)|Classe qui encapsule un objet pouvant être appelé.|  
|[hachage](hash%20Class.md)|Classe qui calcule un code de hachage pour une valeur.|  
|[is_bind_expression](../standard-library/is-bind-expression-class.md)|Classe qui teste si un type particulier est généré en appelant `bind`.|  
|[is_placeholder](../standard-library/is-placeholder-class.md)|Classe qui teste si un type particulier est un espace réservé.|  
|[mem_fun_ref_t](../standard-library/mem-fun-ref-t-class.md)|Une classe d’adaptateur qui permet une **non_const** fonction membre qui n’accepte aucun argument à être appelé comme un objet de fonction unaire lorsque initialisé avec un argument de référence.|  
|[mem_fun_t](../standard-library/mem-fun-t-class.md)|Une classe d’adaptateur qui permet une **non_const** fonction membre qui n’accepte aucun argument à être appelé comme un objet de fonction unaire lorsque initialisé avec un argument de pointeur.|  
|[mem_fun1_ref_t](../standard-library/mem-fun1-ref-t-class.md)|Une classe d’adaptateur qui permet une **non_const** fonction membre qui accepte un argument unique à être appelé comme un objet de fonction binaire lorsque initialisé avec un argument de référence.|  
|[mem_fun1_t](../standard-library/mem-fun1-t-class.md)|Une classe d’adaptateur qui permet une **non_const** fonction membre qui accepte un argument unique à être appelé comme un objet de fonction binaire lorsque initialisé avec un argument de pointeur.|  
|[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md)|Convertit un pointeur de fonction binaire en fonction binaire adaptable.|  
|[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md)|Convertit un pointeur de fonction unaire en fonction unaire adaptable.|  
|[reference_wrapper](../standard-library/reference-wrapper-class.md)|Classe qui encapsule une référence.|  
|[result_of](../standard-library/result-of-class2.md)|Struct qui contient le type de retour d’un objet encapsulé pouvant être appelé.|  
|[unary_negate](../standard-library/unary-negate-class.md)|Classe de modèle fournissant une fonction membre qui inverse la valeur de retour d'une fonction unaire spécifiée.|  
  
### <a name="functions"></a>Fonctions  
  
|||  
|-|-|  
|[lier](../Topic/%3Cfunctional%3E%20functions.md#bind_function)|Lie des arguments à un objet pouvant être appelé.|  
|[bind1st](../Topic/%3Cfunctional%3E%20functions.md#bind1st_function)|Classe de modèle d’assistance qui crée un adaptateur pour convertir un objet de fonction binaire en objet de fonction unaire en liant le premier argument de la fonction binaire à une valeur spécifiée.|  
|[bind2nd](../Topic/%3Cfunctional%3E%20functions.md#bind2nd_function)|Classe de modèle d’assistance qui crée un adaptateur pour convertir un objet de fonction binaire en objet de fonction unaire en liant le second argument de la fonction binaire à une valeur spécifiée.|  
|[BIT_AND](../Topic/%3Cfunctional%3E%20functions.md#bit_and_function)|Retourne le résultat de l'opération AND logique au niveau du bit (opérateur binaire &) des deux paramètres.|  
|[bit_not](../Topic/%3Cfunctional%3E%20functions.md#bit_not_function)|Retourne le complément logique au niveau du bit (opérateur ~) du paramètre.|  
|[BIT_OR](../Topic/%3Cfunctional%3E%20functions.md#bit_or_function)|Retourne le OR logique (opérateur &#124 ;) des deux paramètres.|  
|[BIT_XOR](../Topic/%3Cfunctional%3E%20functions.md#bit_xor_function)|Retourne le résultat de l'opération XOR logique au niveau du bit (opérateur ^) des deux paramètres.|  
|[cref](../Topic/%3Cfunctional%3E%20functions.md#cref_function)|Construit un `reference_wrapper` const à partir d'un argument.|  
|[mem_fn](../Topic/%3Cfunctional%3E%20functions.md#mem_fn_function)|Génère un wrapper d'appel simple.|  
|[mem_fun](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_function)|Fonctions de modèle d’assistance utilisées pour construire des adaptateurs d’objets de fonction pour des fonctions membres en cas d’initialisation avec des arguments de pointeur.|  
|[mem_fun_ref](../Topic/%3Cfunctional%3E%20functions.md#mem_fun_ref_function)|Fonction de modèle d’assistance utilisée pour construire des adaptateurs d’objets de fonction pour des fonctions membres en cas d’initialisation avec des arguments de référence.|  
|[not1](../Topic/%3Cfunctional%3E%20functions.md#not1_function)|Retourne le complément d’un prédicat unaire.|  
|[not2](../Topic/%3Cfunctional%3E%20functions.md#not2_function)|Retourne le complément d’un prédicat binaire.|  
|[ptr_fun](../Topic/%3Cfunctional%3E%20functions.md#ptr_fun_function)|Fonction de modèle d'assistance utilisée pour convertir des pointeurs de fonction unaires et binaires, respectivement dans des fonctions adaptables unaires et binaires.|  
|[ref](../Topic/%3Cfunctional%3E%20functions.md#ref_function)|Construit un `reference_wrapper` à partir d'un argument.|  
|[échange](../Topic/%3Cfunctional%3E%20functions.md#swap_function)|Échange deux objets `function`.|  
  
### <a name="structs"></a>Structures  
  
|||  
|-|-|  
|[binary_function](../standard-library/binary-function-struct.md)|Classe de base vide qui définit des types qui peuvent être héritées par une classe dérivée qui fournit un objet de fonction binaire.|  
|[divise](../standard-library/divides-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération arithmétique de division sur des éléments d'un type valeur spécifié.|  
|[equal_to](../standard-library/equal-to-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié est égale à une autre valeur de ce type.|  
|[supérieur](../standard-library/greater-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié est supérieure à une autre valeur de ce type.|  
|[greater_equal](../standard-library/greater-equal-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié est supérieure ou égale à une autre valeur de ce type.|  
|[moins](../standard-library/less-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié est inférieure à une autre valeur de ce type.|  
|[less_equal](../standard-library/less-equal-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié est inférieure ou égale à une autre valeur de ce type.|  
|[logical_and](../standard-library/logical-and-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération logique de conjonction sur des éléments d'un type valeur spécifié et teste si le résultat est vrai ou faux.|  
|[logical_not](../standard-library/logical-not-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération logique de négation sur des éléments d'un type valeur spécifié et teste si le résultat est vrai ou faux.|  
|[logical_or](../standard-library/logical-or-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération logique de disjonction sur des éléments d'un type valeur spécifié et teste si le résultat est vrai ou faux.|  
|[signe moins](../standard-library/minus-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération arithmétique de soustraction sur des éléments d'un type valeur spécifié.|  
|[modulo](../standard-library/modulus-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération arithmétique de modulo sur des éléments d'un type valeur spécifié.|  
|[Multiplie](../standard-library/multiplies-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération arithmétique de multiplication sur des éléments d'un type valeur spécifié.|  
|[Negate](../standard-library/negate-struct.md)|La classe fournit un objet de fonction prédéfini qui retourne la valeur négative d'une valeur d'élément.|  
|[Not_Equal_To](../standard-library/not-equal-to-struct.md)|Prédicat binaire qui teste si une valeur d’un type spécifié n’est pas égale à une autre valeur de ce type.|  
|[plus (+)](../standard-library/plus-struct.md)|La classe fournit un objet de fonction prédéfini qui effectue l'opération arithmétique d'addition sur des éléments d'un type valeur spécifié.|  
|[unary_function](../standard-library/unary-function-struct.md)|Classe de base vide qui définit des types qui peuvent être héritées par une classe dérivée qui fournit un objet de fonction unaire.|  
  
### <a name="objects"></a>d'entreprise  
  
|||  
|-|-|  
|[_1.._M](../standard-library/1-object.md)|Espaces réservés pour les arguments remplaçables.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur ==](../Topic/%3Cfunctional%3E%20operators.md#operator_eq_eq)|N'autorise pas la comparaison d'égalité d'objets pouvant être appelés.|  
|[opérateur ! =](../Topic/%3Cfunctional%3E%20operators.md#operator_neq)|N'autorise pas la comparaison d'inégalité d'objets pouvant être appelés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque de modèles standard](../misc/standard-template-library.md)

