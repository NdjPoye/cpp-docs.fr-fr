---
title: "&lt;type_traits&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<type_traits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typetrait (en-tête) (TR1)"
  - "type_traits"
ms.assetid: 2260b51f-8160-4c66-a82f-00b534cb60d4
caps.latest.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 35
---
# &lt;type_traits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit des modèles qui fournissent des constantes de compilation qui donnent des informations sur les propriétés de leurs arguments de type ou produisant transformé types.  
  
## Syntaxe  
  
```  
#include <type_traits>  
```  
  
## Notes  
 Les classes et les modèles dans `<type_traits>` sont utilisés pour prendre en charge l’inférence de type, la classification et la transformation au moment de la compilation, pour détecter les erreurs liées au type et pour vous aider à optimiser votre code générique. Ces classes et les modèles incluent unaire traits de types qui décrivent une propriété d’un type, les caractéristiques de type binaire qui décrivent la relation entre les types et les caractéristiques de transformation que vous modifient une propriété d’un type.  
  
 Pour prendre en charge les caractéristiques de type, une classe d’assistance, `integral_constant`, est définie. Il possède des spécialisations de modèle `true_type` et `false_type` qui forment les classes de base pour les prédicats de type. Un *prédicat de type* est un modèle qui prend un ou plusieurs arguments de type. Quand un prédicat de type *contient la valeur true*, il est publiquement dérivé, directement ou indirectement, de [true\_type](../Topic/true_type%20Typedef.md). Quand un prédicat de type*contient la valeur false*, il est publiquement dérivé, directement ou indirectement, de [false\_type](../Topic/false_type%20Typedef.md).  
  
 Un *modificateur de type* ou *caractéristique de transformation* est un modèle qui prend un ou plusieurs arguments de modèle et possède le membre `type`, qui est un synonyme du type modifié.  
  
### Modèles d'alias  
 Pour simplifier les expressions de caractéristiques de type, [modèles d’alias](../cpp/aliases-and-typedefs-cpp.md) pour `typename some_trait<T>::type` sont fournis, où « `some_trait`» est le nom de classe de modèle. Par exemple, [add\_const](../standard-library/add-const-class.md) a un modèle d’alias pour son type, `add_const_t`, défini comme :  
  
```cpp  
template<class T>  
    using add_const_t = typename add_const<T>::type;  
```  
  
|||||  
|-|-|-|-|  
|add\_const\_t|aligned\_storage\_t|make\_signed\_t|remove\_pointer\_t|  
|add\_cv\_t|aligned\_union\_t|make\_unsigned\_t|remove\_reference\_t|  
|add\_lvalue\_reference\_t|common\_type\_t|remove\_all\_extents\_t|remove\_volatile\_t|  
|add\_pointer\_t|conditional\_t|remove\_const\_t|result\_of\_t|  
|add\_rvalue\_reference\_t|decay\_t|remove\_cv\_t|underlying\_type\_t|  
|add\_volatile\_t|enable\_if\_t|remove\_extent\_t||  
  
### Classes  
 Typedefs et classe d’assistance  
  
|||  
|-|-|  
|[integral\_constant](../standard-library/integral-constant-class-bool-constant-class.md)|Rend un intégral constant à partir d’un type et une valeur.|  
|[true\_type](../Topic/true_type%20Typedef.md)|Contient une constante intégrale avec la valeur true.|  
|[false\_type](../Topic/false_type%20Typedef.md)|Contient une constante intégrale avec la valeur false.|  
  
 Catégories de type principal  
  
|||  
|-|-|  
|[is\_void](../standard-library/is-void-class.md)|Teste si le type est `void`.|  
|[is\_null\_pointer](../standard-library/is-null-pointer-class.md)|Teste si le type est `std::nullptr_t`.|  
|[is\_integral](../standard-library/is-integral-class.md)|Teste si le type est intégral.|  
|[is\_floating\_point](../standard-library/is-floating-point-class.md)|Teste si le type est à virgule flottante.|  
|[is\_array](../standard-library/is-array-class.md)|Teste si le type est un tableau.|  
|[is\_pointer](../standard-library/is-pointer-class.md)|Teste si le type est un pointeur.|  
|[is\_lvalue\_reference](../standard-library/is-lvalue-reference-class.md)|Teste si le type est une référence lvalue.|  
|[is\_rvalue\_reference](../standard-library/is-rvalue-reference-class.md)|Teste si le type est une référence rvalue.|  
|[is\_member\_object\_pointer](../standard-library/is-member-object-pointer-class.md)|Teste si le type est un pointeur vers un objet membre.|  
|[is\_member\_function\_pointer](../standard-library/is-member-function-pointer-class.md)|Teste si le type est un pointeur vers une fonction membre.|  
|[is\_enum](../standard-library/is-enum-class.md)|Teste si le type est une énumération.|  
|[is\_union](../standard-library/is-union-class.md)|Teste si le type est une union.|  
|[is\_class](../standard-library/is-class-class.md)|Teste si le type est une classe.|  
|[is\_function](../standard-library/is-function-class.md)|Teste si le type est un type de fonction.|  
  
 Catégories de type composite  
  
|||  
|-|-|  
|[is\_reference](../standard-library/is-reference-class.md)|Teste si le type est une référence.|  
|[is\_arithmetic](../standard-library/is-arithmetic-class.md)|Teste si le type est arithmétique.|  
|[is\_fundamental](../standard-library/is-fundamental-class.md)|Teste si le type est `void` ou arithmétique.|  
|[is\_object](../standard-library/is-object-class.md)|Teste si le type est un type d'objet.|  
|[is\_scalar](../standard-library/is-scalar-class.md)|Teste si le type est scalaire.|  
|[is\_compound](../standard-library/is-compound-class.md)|Teste si le type n'est pas scalaire.|  
|[is\_member\_pointer](../standard-library/is-member-pointer-class.md)|Teste si le type est un pointeur vers un membre.|  
  
 Propriétés de type  
  
|||  
|-|-|  
|[is\_const](../standard-library/is-const-class.md)|Teste si le type est `const`.|  
|[is\_volatile](../standard-library/is-volatile-class.md)|Teste si le type est `volatile`.|  
|[is\_trivial](../standard-library/is-trivial-class.md)|Teste si le type est simple.|  
|[is\_trivially\_copyable](../standard-library/is-trivially-copyable-class.md)|Teste si le type est susceptible d’être simplement copié.|  
|[is\_standard\_layout](../standard-library/is-standard-layout-class.md)|Teste si le type est un type de mise en forme standard.|  
|[is\_pod](../standard-library/is-pod-class.md)|Teste si le type est POD.|  
|[is\_literal\_type](../standard-library/is-literal-type-class.md)|Teste si le type peut être un `constexpr` variable ou utilisées dans un `constexpr` \(fonction\).|  
|[is\_empty](../standard-library/is-empty-class.md)|Teste si le type est une classe vide.|  
|[is\_polymorphic](../standard-library/is-polymorphic-class.md)|Teste si le type est une classe polymorphe.|  
|[is\_abstract](../standard-library/is-abstract-class.md)|Teste si le type est une classe abstraite.|  
|[is\_final](../standard-library/is-final-class.md)|Teste si le type est un type de classe marqué `final`.|  
|[is\_signed](../standard-library/is-signed-class.md)|Teste si le type est un entier signé.|  
|[is\_unsigned](../standard-library/is-unsigned-class.md)|Teste si le type est un entier non signé.|  
|[is\_constructible](../standard-library/is-constructible-class.md)|Teste si le type peut être construit à l’aide des types d’arguments spécifiés.|  
|[is\_default\_constructible](../standard-library/is-default-constructible-class.md)|Teste si le type a un constructeur par défaut.|  
|[is\_copy\_constructible](../standard-library/is-copy-constructible-class.md)|Teste si le type a un constructeur de copie.|  
|[is\_move\_constructible](../standard-library/is-move-constructible-class.md)|Teste si le type a un constructeur de déplacement.|  
|[is\_assignable](../standard-library/is-assignable-class.md)|Teste si le premier type peut avoir une valeur du second type.|  
|[is\_copy\_assignable](../standard-library/is-copy-assignable-class.md)|Teste si un type peut être affecté à une valeur de référence const de type.|  
|[is\_move\_assignable](../standard-library/is-move-assignable-class.md)|Teste si un type peut être assigné à une référence rvalue du type.|  
|[is\_destructible](../standard-library/is-destructible-class.md)|Teste si le type est destructible.|  
|[is\_trivially\_constructible](../standard-library/is-trivially-constructible-class.md)|Teste si le type n’utilise aucune opération non triviale lorsque construite à l’aide des types spécifiés.|  
|[is\_trivially\_default\_constructible](../standard-library/is-trivially-default-constructible-class.md)|Teste si le type n’utilise aucune opération non triviale lors de la construction par défaut.|  
|[is\_trivially\_copy\_constructible](../standard-library/is-trivially-copy-constructible-class.md)|Teste si le type n’utilise aucune opération non triviale lors de la construction de copie.|  
|[is\_trivially\_move\_constructible](../standard-library/is-trivially-move-constructible-class.md)|Teste si le type n’utilise aucune opération non triviale lors de la construction de déplacement.|  
|[is\_trivially\_assignable](../standard-library/is-trivially-assignable-class.md)|Teste si les types peuvent être assignés et l’affectation n’utilise aucune opération non triviale.|  
|[is\_trivially\_copy\_assignable](../standard-library/is-trivially-copy-assignable-class.md)|Teste si le type n’est assignable copie et l’affectation utilise aucune opération non triviale.|  
|[is\_trivially\_move\_assignable](../standard-library/is-trivially-move-assignable-class.md)|Teste si le type n’est assignable de déplacement et l’affectation utilise aucune opération non triviale.|  
|[is\_trivially\_destructible](../standard-library/is-trivially-destructible-class.md)|Teste si le type est destructibles et le destructeur n’utilise aucune opération non triviale.|  
|[is\_nothrow\_constructible](../standard-library/is-nothrow-constructible-class.md)|Teste si le type est constructible et ne connaît ne pas lever lorsque construite à l’aide des types spécifiés.|  
|[is\_nothrow\_default\_constructible](../standard-library/is-nothrow-default-constructible-class.md)|Tests si le type est default constructible et ne connaît ne pas lever lors de la construction par défaut.|  
|[is\_nothrow\_copy\_constructible](../standard-library/is-nothrow-copy-constructible-class.md)|Teste si le type est constructible copie et le constructeur de copie ne connaît ne pas lever.|  
|[is\_nothrow\_move\_constructible](../standard-library/is-nothrow-move-constructible-class.md)|Teste si le type est constructible déplacement et le constructeur de déplacement ne connaît ne pas lever.|  
|[is\_nothrow\_assignable](../standard-library/is-nothrow-assignable-class.md)|Teste si le type ne peut être assigné à l’aide du type spécifié et l’affectation ne connaît ne pas lever.|  
|[is\_nothrow\_copy\_assignable](../standard-library/is-nothrow-copy-assignable-class.md)|Teste si le type est assignable copie et l’affectation ne connaît ne pas lever.|  
|[is\_nothrow\_move\_assignable](../standard-library/is-nothrow-move-assignable-class.md)|Teste si le type est assignable de déplacement et l’affectation ne connaît ne pas lever.|  
|[is\_nothrow\_destructible](../standard-library/is-nothrow-destructible-class.md)|Teste si le type est destructibles et le destructeur ne connaît ne pas lever.|  
|[has\_virtual\_destructor](http://msdn.microsoft.com/fr-fr/c0f85f0b-c63c-410d-a046-72eeaf44f7eb)|Teste si le type a un destructeur virtuel.|  
  
 Requêtes de propriété de type  
  
|||  
|-|-|  
|[alignment\_of](../standard-library/alignment-of-class.md)|Obtient l’alignement d’un type.|  
|[rank](../standard-library/rank-class.md)|Obtient le nombre de dimensions de tableau.|  
|[extent](../standard-library/extent-class.md)|Obtient le nombre d’éléments dans la dimension du tableau spécifié.|  
  
 Relations de type  
  
|||  
|-|-|  
|[is\_same](../standard-library/is-same-class.md)|Teste si deux types sont identiques.|  
|[is\_base\_of](../standard-library/is-base-of-class.md)|Teste si un type est une base d’un autre.|  
|[is\_convertible](../standard-library/is-convertible-class.md)|Teste si un type est convertible en un autre.|  
  
 Modifications de const\-volatile  
  
|||  
|-|-|  
|[add\_const](../standard-library/add-const-class.md)|Génère un `const` type type.|  
|[add\_volatile](../standard-library/add-volatile-class.md)|Génère un `volatile` type type.|  
|[add\_cv](../standard-library/add-cv-class.md)|Génère une `const``volatile` type type.|  
|[remove\_const](../standard-library/remove-const-class.md)|Génère un type non\-const de type.|  
|[remove\_volatile](../standard-library/remove-volatile-class.md)|Génère un type non volatile du type.|  
|[remove\_cv](../standard-library/remove-cv-class.md)|Génère un type non volatile de non\-const de type.|  
  
 Modifications de la référence  
  
|||  
|-|-|  
|[add\_lvalue\_reference](../standard-library/add-lvalue-reference-class.md)|Génère une référence au type du type.|  
|[add\_rvalue\_reference](../standard-library/add-rvalue-reference-class.md)|Génère une référence rvalue au type à partir du type|  
|[remove\_reference](../standard-library/remove-reference-class.md)|Génère un type sans référence de type.|  
  
 Modifications de l’authentification  
  
|||  
|-|-|  
|[make\_signed](../standard-library/make-signed-class.md)|Génère le type si connecté ou le plus petit type signé supérieur ou égal en taille au type.|  
|[make\_unsigned](../standard-library/make-unsigned-class.md)|Génère le type si non signées ou le plus petit type non signé supérieur ou égal en taille au type.|  
  
 Modifications de tableau  
  
|||  
|-|-|  
|[remove\_all\_extents](../standard-library/remove-all-extents-class.md)|Génère un type non\-tableau à partir d’un type tableau.|  
|[remove\_extent](../standard-library/remove-extent-class.md)|Génère le type d’élément d’un type tableau.|  
  
 Modifications de pointeur  
  
|||  
|-|-|  
|[add\_pointer](../standard-library/add-pointer-class.md)|Génère un pointeur vers le type du type.|  
|[remove\_pointer](../standard-library/remove-pointer-class.md)|Génère un type d’un pointeur vers le type.|  
  
 Autres transformations  
  
|||  
|-|-|  
|[aligned\_storage](../standard-library/aligned-storage-class.md)|Alloue la mémoire non initialisée pour un type aligné.|  
|[aligned\_union](../standard-library/aligned-union-class.md)|Alloue la mémoire non initialisée pour une union alignée avec un constructeur ou un destructeur non trivial.|  
|[common\_type](../standard-library/common-type-class.md)|Génère le type commun de tous les types du pack de paramètre.|  
|[conditional](../standard-library/conditional-class.md)|Si la condition est true, génère le premier type spécifié, sinon le second type spécifié.|  
|[decay](../standard-library/decay-class.md)|Génère le type passés par valeur. Crée un type non\-référence, non const ou non volatile, ou crée un pointeur vers un type.|  
|[enable\_if](../standard-library/enable-if-class.md)|Si la condition est true, ne génère le type spécifié, sinon aucun type.|  
|[result\_of](../standard-library/result-of-class1.md)|Détermine le type de retour de type peut être appelé qui accepte les types d’arguments spécifiés.|  
|[underlying\_type](../standard-library/underlying-type-class.md)|Génère le type intégral sous\-jacent pour un type d’énumération.|  
  
## Voir aussi  
 [\<functional\>](../standard-library/functional.md)