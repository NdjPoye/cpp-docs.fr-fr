---
title: __declspec | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __declspec_cpp
- __declspec
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++]
ms.assetid: 832db681-e8e1-41ca-b78c-cd9d265cdb87
caps.latest.revision: 12
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
ms.openlocfilehash: b29b6243611f1ca59a579869469c803d3735f9df
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="declspec"></a>__declspec
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 La syntaxe à attributs étendus pour la spécification des informations de classe de stockage utilise le mot clé `__declspec`, ce qui indique qu'une instance d'un type donné doit être stockée avec un attribut de classe de stockage Microsoft répertorié ci-dessous. Parmi les exemples d'autres modificateurs de classe de stockage figurent les mots clés `static` et `extern`. Toutefois, ces mots clés font partie de la spécification ANSI des langages C et C++ et, en tant que tels, ne sont pas couverts par la syntaxe à attributs étendus. La syntaxe à attributs étendus simplifie et normalise les extensions spécifiques à Microsoft pour les langages C et C++.  
  
## <a name="grammar"></a>Grammaire  
 *spécificateur de déclaration*:  
 `__declspec (`  *Extended-decl-modifier-seq*  `)`  
  
 *extended-decl-modifier-seq* :  
 *extended-decl-modifier*opt  
  
 *Extended-decl-modifier extended-decl-modifier-seq*  
  
 *extended-decl-modifier* :  
 `align(` *#* `)`  
  
 `allocate("`*segname*`")`  
  
 `appdomain`  
  
 `code_seg("`*segname*`")`  
  
 `deprecated`  
  
 `dllimport`  
  
 `dllexport`  
  
 `jitintrinsic`  
  
 `naked`  
  
 `noalias`  
  
 `noinline`  
  
 `noreturn`  
  
 `nothrow`  
  
 `novtable`  
  
 `process`  
  
 `property(`{`get=`*get_func_name*&#124;`,put=` *put_func_name*}`)`  
  
 `restrict`  
  
 `safebuffers`  
  
 `selectany`  
  
 `thread`  
  
 `uuid("`*ComObjectGUID*`")`  
  
 Un espace blanc sépare la séquence de modificateur de déclaration. Des exemples sont donnés dans des sections ultérieures.  
  
 Ces attributs de classe de stockage spécifique à Microsoft prend en charge la grammaire de l’attribut étendu : [aligner](../cpp/align-cpp.md), [allouer](../cpp/allocate.md), [appdomain](../cpp/appdomain.md), [code_seg](../cpp/code-seg-declspec.md), [déconseillée](../cpp/deprecated-cpp.md), [dllexport](../cpp/dllexport-dllimport.md), [dllimport](../cpp/dllexport-dllimport.md), [jitintrinsic](../cpp/jitintrinsic.md), [naked](../cpp/naked-cpp.md), [noalias](../cpp/noalias.md), [noinline](../cpp/noinline.md), [noreturn](../cpp/noreturn.md), [nothrow](../cpp/nothrow-cpp.md), [novtable](../cpp/novtable.md) , [processus](../cpp/process.md), [restreindre](../cpp/restrict.md), [safebuffers](../cpp/safebuffers.md), [selectany](../cpp/selectany.md), et [thread](../cpp/thread.md). Il prend également en charge ces attributs d’objet COM : [propriété](../cpp/property-cpp.md) et [uuid](../cpp/uuid-cpp.md).  
  
 Les attributs de classe de stockage `code_seg`, `dllexport`, `dllimport`, `naked`, `noalias`, `nothrow`, `property`, `restrict`, `selectany`, `thread` et `uuid` sont des propriétés uniquement de la déclaration de l'objet ou de la fonction à laquelle ils s'appliquent. L'attribut `thread` affecte uniquement les données et les objets. L'attribut `naked` affecte uniquement les fonctions. Les attributs `dllimport` et `dllexport` affectent les fonctions, les données et les objets. Les attributs `property`, `selectany` et `uuid` affectent les objets COM.  
  
 Les mots clés `__declspec` doivent être placés au début d'une déclaration simple. Le compilateur ignore sans avertissement les mots clés `__declspec` placés après * ou & et devant l'identificateur de variable dans une déclaration.  
  
 Un attribut `__declspec` spécifié au début d'une déclaration de type défini par l'utilisateur s'applique à la variable de ce type. Exemple :  
  
```  
__declspec(dllimport) class X {} varX;  
```  
  
 Dans ce cas, l'attribut s'applique à `varX`. Un attribut `__declspec` placé après le mot clé `class` ou `struct` s'applique au type défini par l'utilisateur. Exemple :  
  
```  
class __declspec(dllimport) X {};  
```  
  
 Dans ce cas, l'attribut s'applique à `X`.  
  
 La recommandation générale en matière d'utilisation de l'attribut `__declspec` pour les déclarations simples est la suivante :  
  
```  
  
decl-specifier-seq  
declarator-list;  
```  
  
 Le *decl-specifier-seq* doit contenir, entre autres choses, un type de base (par exemple, `int`, `float`, un `typedef`, ou un nom de classe), une classe de stockage (par exemple, `static`, `extern`), ou la `__declspec`extension. Le *init-declarator-list* doit contenir, entre autres choses, le pointeur de déclarations. Exemple :  
  
```  
__declspec(selectany) int * pi1 = 0;   //OK, selectany & int both part of decl-specifier  
int __declspec(selectany) * pi2 = 0;   //OK, selectany & int both part of decl-specifier  
int * __declspec(selectany) pi3 = 0;   //ERROR, selectany is not part of a declarator  
```  
  
 Le code suivant déclare une variable locale de thread entière et lui affecte une valeur initiale :  
  
```  
// Example of the __declspec keyword  
__declspec( thread ) int tls_i = 1;  
```  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Attributs étendus de classe de stockage C](../c-language/c-extended-storage-class-attributes.md)
