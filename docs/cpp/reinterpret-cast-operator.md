---
title: "Opérateur reinterpret_cast | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: reinterpret_cast_cpp
dev_langs: C++
helpviewer_keywords: reinterpret_cast keyword [C++]
ms.assetid: eb3283c7-7f88-467e-affd-407d37b46d6c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0957a696d7675a932aa86531d39f2e4895ba1ff9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="reinterpretcast-operator"></a>reinterpret_cast, opérateur
Autorise la conversion de tout pointeur en tout autre type pointeur. Autorise également la conversion de tout type entier en tout type pointeur et vice versa.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
reinterpret_cast < type-id > ( expression )  
```  
  
## <a name="remarks"></a>Notes  
 L'utilisation incorrecte de l'opérateur `reinterpret_cast` peut facilement présenter un risque. À moins que la conversion souhaitée soit fondamentalement de bas niveau, vous devez utiliser l'un des autres opérateurs de cast.  
  
 L'opérateur `reinterpret_cast` peut être utilisé pour des conversions comme `char*` en `int*`, ou `One_class*` en `Unrelated_class*`, qui sont fondamentalement risquées.  
  
 Le résultat de `reinterpret_cast` ne peut pas être utilisé sans risque pour autre chose qu'une reconversion vers son type d'origine. Les autres utilisations sont, au mieux, non portables.  
  
 Le `reinterpret_cast` opérateur ne peut pas caster la **const**, `volatile`, ou **__unaligned** attributs. Consultez [opérateur const_cast](../cpp/const-cast-operator.md) pour plus d’informations sur la suppression de ces attributs.  
  
 L'opérateur `reinterpret_cast` convertit une valeur de pointeur null en la valeur de pointeur null du type de destination.  
  
 L'une des utilisations pratiques de `reinterpret_cast` concerne les fonctions de hachage, qui mappent une valeur à un index de telle sorte que deux valeurs distinctes finissent rarement avec le même index.  
  
```  
#include <iostream>  
using namespace std;  
  
// Returns a hash code based on an address  
unsigned short Hash( void *p ) {  
   unsigned int val = reinterpret_cast<unsigned int>( p );  
   return ( unsigned short )( val ^ (val >> 16));  
}  
  
using namespace std;  
int main() {  
   int a[20];  
   for ( int i = 0; i < 20; i++ )  
      cout << Hash( a + i ) << endl;  
}  
  
Output:   
64641  
64645  
64889  
64893  
64881  
64885  
64873  
64877  
64865  
64869  
64857  
64861  
64849  
64853  
64841  
64845  
64833  
64837  
64825  
64829  
```  
  
 `reinterpret_cast` permet de traiter le pointeur comme un type intégral. Le résultat binaire est alors déplacé et soumis à une opération XOR avec lui-même pour produire un index unique (à un niveau de probabilité élevé). L’index est ensuite tronqué par un cast de style C standard en type de retour de la fonction.  
  
## <a name="see-also"></a>Voir aussi  
 [Opérateurs de casting](../cpp/casting-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)