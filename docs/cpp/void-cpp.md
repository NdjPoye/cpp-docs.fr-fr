---
title: void (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
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
ms.openlocfilehash: dea06f16979fab9aa4494b172d6d95193a9f3727
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="void-c"></a>void (C++)
Quand il est utilisé en tant que type de retour de fonction, le mot clé `void` spécifie que la fonction ne retourne pas de valeur. Quand il est utilisé pour la liste des paramètres d'une fonction, void spécifie que la fonction ne prend aucun paramètre. Quand il est utilisé dans la déclaration d'un pointeur, void spécifie que le pointeur est « universel ».  
  
 Si le type de pointeur est **void \* **, le pointeur peut pointer vers n’importe quelle variable qui n’est pas déclaré avec le **const** ou `volatile` (mot clé). Un pointeur void ne peut pas être déréférencé, sauf s'il fait l'objet d'un cast en un autre type. Un pointeur void peut être converti en tout autre type de pointeur de données.  
  
 Un pointeur void peut pointer vers une fonction, mais pas vers un membre de classe en C++.  
  
 Vous ne pouvez pas déclarer une variable de type void.  
  
## <a name="example"></a>Exemple  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## <a name="see-also"></a>Voir aussi  
 [Mots clés](../cpp/keywords-cpp.md)   
 [Types fondamentaux](../cpp/fundamental-types-cpp.md)
