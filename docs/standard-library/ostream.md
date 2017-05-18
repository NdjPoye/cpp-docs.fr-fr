---
title: '&lt;ostream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<ostream>
- <ostream>
- ostream/std::<ostream>
- std::<ostream>
dev_langs:
- C++
helpviewer_keywords:
- ostream header
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 4b8e9c4f86ac9bab261824c10a8e6d8c3506bc1a
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltostreamgt"></a>&lt;ostream&gt;
Définit la classe de modèle [basic_ostream](../standard-library/basic-ostream-class.md), qui sert d’intermédiaire pour les insertions des iostreams. L'en-tête définit également plusieurs manipulateurs associés. Cet en-tête est généralement inclus pour vous par l’un des autres en-têtes iostream. Vous devez rarement l'inclure directement.)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <ostream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[ostream](../standard-library/ostream-typedefs.md#ostream)|Crée un type à partir de `basic_ostream` qui est spécialisé sur `char` et `char_traits` spécialisé sur `char`.|  
|[wostream](../standard-library/ostream-typedefs.md#wostream)|Crée un type à partir de `basic_ostream` qui est spécialisé sur `wchar_t` et `char_traits` spécialisé sur `wchar_t`.|  
  
### <a name="manipulators"></a>Manipulateurs  
  
|||  
|-|-|  
|[endl](../standard-library/ostream-functions.md#endl)|Met fin à une ligne et vide la mémoire tampon.|  
|[ends](../standard-library/ostream-functions.md#ends)|Met fin à une chaîne.|  
|[flush](../standard-library/ostream-functions.md#flush)|Vide la mémoire tampon.|  
|[swap](../standard-library/ostream-functions.md#swap)|Échange les valeurs du paramètre d'objet `basic_ostream` de gauche avec celles du paramètre d'objet `basic_ostream` de droite.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[operator<<](../standard-library/ostream-operators.md#op_lt_lt)|Écrit différents types dans le flux.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[basic_ostream](../standard-library/basic-ostream-class.md)|La classe de modèle décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)




