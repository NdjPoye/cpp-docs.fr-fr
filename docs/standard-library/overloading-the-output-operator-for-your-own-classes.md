---
title: "Surcharge de l’opérateur &lt;&lt; pour vos propres classes | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 12
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 22eb3fbef373c2e80989c49887cfa8b3c9eadc61
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Surcharge de l’opérateur &lt;&lt; pour vos propres classes
Les flux de sortie utilisent l’opérateur d’insertion (`<<`) pour les types standard. Vous pouvez aussi surcharger l’opérateur `<<` pour vos propres classes.  
  
## <a name="example"></a>Exemple  
 L’exemple de fonction `write` a montré l’utilisation d’une structure `Date`. Les dates sont une parfaite illustration de classe C++ dans laquelle les membres de données (mois, jour et année) sont masqués. Un flux de sortie est la destination logique pour l’affichage d’une structure de ce type. Ce code affiche une date à l’aide de l’objet `cout` :  
  
```  
Date dt(1, 2, 92);

cout <<dt;  
```  
  
 Pour que `cout` accepte un objet `Date` après l’opérateur d’insertion, surchargez l’opérateur d’insertion pour reconnaître un objet `ostream` à gauche et un objet `Date` à droite. La fonction d’opérateur `<<` surchargé doit ensuite être déclarée comme ami (friend) de la classe `Date` pour pouvoir accéder aux données privées dans un objet `Date`.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
```Output  
5/6/92  
```  
  
## <a name="remarks"></a>Notes  
 L’opérateur surchargé retourne une référence à l’objet `ostream` d’origine, ce qui signifie que vous pouvez combiner des insertions :  
  
```  
cout <<"The date is" <<dt <<flush;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)


