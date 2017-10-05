---
title: restreindre (C++ AMP) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- cpu_CPP
- amp_CPP
dev_langs:
- C++
helpviewer_keywords:
- restrict clause (C++ AMP)
ms.assetid: 07d3291f-7edf-456b-8828-283ac8673661
caps.latest.revision: 22
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
ms.openlocfilehash: 13c07d1bb085663abe9492d92835b9e05b89c742
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="restrict-c-amp"></a>restrict (C++ AMP)
Le spécificateur de restriction peut être appliqué aux déclarations de fonctions et lambda. Il applique des restrictions au code dans la fonction et sur le comportement de cette fonction dans les applications qui utilisent le runtime C++ Accelerated Massive Parallelism (C++ AMP).  
  
> [!NOTE]
>  Pour plus d’informations sur la `restrict` mot clé qui fait partie de la `__declspec` des attributs de classe de stockage, consultez [restreindre](../cpp/restrict.md).  
  
 La clause `restrict` prend les formes suivantes :  
  
|Clause|Description|  
|------------|-----------------|  
|`restrict(cpu)`|La fonction peut utiliser le langage C++ complet. Seules les autres fonctions déclarées en utilisant des fonctions restrict(cpu) peuvent appeler la fonction.|  
|`restrict(amp)`|La fonction peut uniquement utiliser le sous-ensemble du langage C++ que C++ AMP peut accélérer.|  
|Séquence de clauses `restrict(cpu)` et `restrict(amp)`|La fonction doit adhérer aux limitations des clauses `restrict(cpu)` et `restrict(amp)`. La fonction peut être appelée par les fonctions déclarées au moyen de `restrict(cpu)`, `restrict(amp)`, `restrict(cpu, amp)` ou `restrict(amp, cpu)`.<br /><br /> L'expression `restrict(A) restrict(B)` peut être écrite `restrict(A,B)`.|  
  
## <a name="remarks"></a>Remarques  
 Le mot clé `restrict` est un mot clé contextuel. Les spécificateurs de restrictions, `cpu` et `amp`, ne sont pas des mots réservés. La liste des spécificateurs n'est pas extensible. Une fonction qui n'a pas de clause `restrict` est identique à une fonction qui possède la clause `restrict(cpu)`.  
  
 Une fonction qui possède la clause `restrict(amp)` présente les limitations suivantes :  
  
-   La fonction peut appeler uniquement des fonctions qui possèdent la clause `restrict(amp)`.  
  
-   La fonction doit être en mesure d'être inline.  
  
-   La fonction peut déclarer uniquement des variables `int`, `unsigned int`, `float` et `double`, ainsi que des classes et des structures contenant uniquement ces types. Le type `bool` est également autorisé, mais il doit être aligné sur 4 octets si vous l'utilisez dans un type composite.  
  
-   Les fonctions lambda ne peuvent pas capturer par référence et ne peuvent pas capturer les pointeurs.  
  
-   Les références et les pointeurs à une seule indirection sont pris en charge uniquement en tant que variables locales, arguments de fonction ou types de retour.  
  
-   Les éléments suivants ne sont pas autorisés :  
  
    -   récurrence,  
  
    -   Les variables déclarées avec le [volatile](../cpp/volatile-cpp.md) (mot clé).  
  
    -   fonctions virtuelles,  
  
    -   pointeurs désignant des fonctions,  
  
    -   pointeurs désignant des fonctions membres,  
  
    -   pointeurs dans des structures,  
  
    -   pointeurs désignant des pointeurs,  
  
    -   instructions `goto`,  
  
    -   instructions étiquetées,  
  
    -   instructions `try`, `catch` et `throw`,  
  
    -   Variables globales.  
  
    -   variables statiques Utilisez [tile_static, mot clé](../cpp/tile-static-keyword.md) à la place.  
  
    -   casts `dynamic_cast`,  
  
    -   opérateur `typeid`,  
  
    -   déclarations asm,  
  
    -   varargs.  
  
 Pour en savoir plus sur les limitations de fonction, consultez [Restrict (amp) Restrictions](http://go.microsoft.com/fwlink/p/?LinkId=251089).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser le `restrict(amp)`clause.  
  
```  
  
void functionAmp() restrict(amp) {}   
void functionNonAmp() {}   
  
void callFunctions() restrict(amp)   
{   
    // int is allowed.  
    int x;  
    // long long int is not allowed in an amp-restricted function. This generates a compiler error.  
    // long long int y;   
  
    // Calling an amp-restricted function is allowed.  
    functionAmp();   
  
    // Calling a non-amp-restricted function is not allowed.  
    // functionNonAmp();   
  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)
