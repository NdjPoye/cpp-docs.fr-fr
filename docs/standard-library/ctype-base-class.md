---
title: ctype_base, classe| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::ctype_base
- ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 59ec50c7e68b4d79b97218a8cd24df391198e758
ms.lasthandoff: 02/24/2017

---
# <a name="ctypebase-class"></a>ctype_base, classe
La classe sert de classe de base pour les facettes de la classe de modèle [ctype](../standard-library/ctype-class.md). Classe de base de la classe ctype utilisée pour définir des types énumération utilisés pour classifier ou tester les caractères, individuellement ou dans des plages entières.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct ctype_base : public locale::facet
{
    enum
 {
    alnum,
 alpha,
    cntrl,
 digit,
    graph,
 lower,
    print,
 punct,
    space,
 upper,
    xdigit
 };
    typedef short mask;
    ctype_base(
 size_t _Refs = 0);

 ~ctype_base();

};
```  
  
## <a name="remarks"></a>Notes  
 Elle définit un masque d’énumération. Chaque constante d’énumération caractérise une méthode de classification des caractères, comme défini par les fonctions avec des noms similaires déclarées dans l’en-tête \<ctype.h>. Les constantes sont :  
  
- **space** (fonction [isspace](../standard-library/locale-functions.md#isspace))  
  
- **print** (fonction [isprint](../standard-library/locale-functions.md#isprint))  
  
- **cntrl** (fonction [iscntrl](../standard-library/locale-functions.md#iscntrl))  
  
- **upper** (fonction [isupper](../standard-library/locale-functions.md#isupper))  
  
- **lower** (fonction [islower](../standard-library/locale-functions.md#islower))  
  
- **digit** (fonction [isdigit](../standard-library/locale-functions.md#isdigit))  
  
- **punct** (fonction [ispunct](../standard-library/locale-functions.md#ispunct))  
  
- **xdigit** (fonction [isxdigit](../standard-library/locale-functions.md#isxdigit))  
  
- **alpha** (fonction [isalpha](../standard-library/locale-functions.md#isalpha))  
  
- **alnum** (fonction [isalnum](../standard-library/locale-functions.md#isalnum))  
  
- **graph** (fonction [isgraph](../standard-library/locale-functions.md#isgraph))  
  
 Vous pouvez caractériser une combinaison de classifications en reliant ces constantes par une opération OR. En particulier, ce qui suit est toujours vérifié : **alnum** == ( **alpha**``&#124; **digit**\) and **graph** \=\= \( **alnum**``&#124; **punct**).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<locale>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




