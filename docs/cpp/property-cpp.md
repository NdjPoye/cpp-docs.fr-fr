---
title: "propriété (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- property_cpp
dev_langs:
- C++
helpviewer_keywords:
- property __declspec keyword
- __declspec keyword [C++], property
ms.assetid: f3b850ba-bf48-4df7-a1d6-8259d97309ce
caps.latest.revision: 7
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
ms.openlocfilehash: d4cb68d02f9ee543c2d3271bc48ad4318352faa2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="property-c"></a>property (C++)
**Section spécifique à Microsoft**  
  
 Cet attribut peut être appliqué à des « données membres virtuelles » non statiques dans une définition de classe ou de structure. Le compilateur traite ces « données membres virtuelles » comme des données membres en changeant leurs références en appels de fonction.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      __declspec( property( get=get_func_name ) ) declarator  
__declspec( property( put=put_func_name ) ) declarator  
__declspec( property( get=get_func_name, put=put_func_name ) ) declarator  
```  
  
## <a name="remarks"></a>Remarques  
 Lorsque le compilateur détecte une donnée membre déclarée avec cet attribut sur la droite d’un opérateur de sélection de membres («**.**« ou »**->**»), il convertit l’opération à un **obtenir** ou **put** fonction, selon que cette expression est une l-value ou une r-value. Plus compliquée contextes, tels que «`+=`», une réécriture est effectuée en exécutant les deux **obtenir** et **put**.  
  
 Cet attribut peut également être utilisé dans la déclaration d'un tableau vide dans une définition de classe ou de structure. Exemple :  
  
```  
__declspec(property(get=GetX, put=PutX)) int x[];  
```  
  
 L'instruction ci-dessus indique que `x[]` peut être utilisé avec un ou plusieurs index de tableau. Dans ce cas, `i=p->x[a][b]` est converti en `i=p->GetX(a, b)` et `p->x[a][b] = i` est converti en `p->PutX(a, b, i);`  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="example"></a>Exemple  
  
```  
// declspec_property.cpp  
struct S {  
   int i;  
   void putprop(int j) {   
      i = j;  
   }  
  
   int getprop() {  
      return i;  
   }  
  
   __declspec(property(get = getprop, put = putprop)) int the_prop;  
};  
  
int main() {  
   S s;  
   s.the_prop = 5;  
   return s.the_prop;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)
