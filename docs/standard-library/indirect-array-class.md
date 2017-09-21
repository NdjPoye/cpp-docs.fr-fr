---
title: indirect_array, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::indirect_array
- indirect_array
dev_langs:
- C++
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
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
ms.openlocfilehash: 7a5b105b9c812d81dfbbe5905bb593bba1b98ef8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="indirectarray-class"></a>indirect_array, classe
Classe de modèle interne auxiliaire qui prend en charge les objets qui sont des sous-ensembles de valarrays en fournissant des opérations entre des tableaux de sous-ensembles définis en spécifiant un sous-ensemble d'index d'un valarray parent.  
  
## <a name="syntax"></a>Syntaxe  
  
  
  
## <a name="remarks"></a>Notes  
 Cette classe décrit un objet qui stocke une référence à un objet **va** de classe [valarray](../standard-library/valarray-class.md)**\<Type>**, ainsi qu’un objet **xa** de classe **valarray<size_t>**, qui décrit la séquence d’éléments à sélectionner à partir de l’objet **valarray\<Type>**.  
  
 Vous construisez un objet **indirect_array\<Type>** uniquement en écrivant une expression sous la forme **va[xa]**. Les fonctions membres de classe indirect_array se comportent ensuite comme les signatures de fonctions correspondantes définies pour **valarray\<Type>**, sauf que seule la séquence d’éléments sélectionnée est affectée.  
  
 La séquence se compose de **xa.**[size](../standard-library/valarray-class.md#size) éléments, où l’élément `I` devient l’index **xa**[ `I`] dans **va**.  
  
## <a name="example"></a>Exemple :  
  
```  
// indirect_array.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // Select 2nd, 4th & 6th elements  
   // and assign a value of 10 to them  
   valarray<size_t> indx ( 3 );  
   indx [0] = 2;  
   indx [1] = 4;  
   indx [2] = 6;  
   va[indx] = 10;  
  
   cout << "The modified operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
### <a name="output"></a>Sortie  
  
```  
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).  
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<valarray>  
  
 **Espace de noms :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

