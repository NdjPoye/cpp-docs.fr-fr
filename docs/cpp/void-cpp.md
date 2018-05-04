---
title: void (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de70ec6758109bc765d0cec3552762288d51ded2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="void-c"></a>void (C++)
Quand il est utilisé en tant que type de retour de fonction, le mot clé `void` spécifie que la fonction ne retourne pas de valeur. Quand il est utilisé pour la liste des paramètres d'une fonction, void spécifie que la fonction ne prend aucun paramètre. Quand il est utilisé dans la déclaration d'un pointeur, void spécifie que le pointeur est « universel ».  
  
 Si le type de pointeur est **void \***, le pointeur peut pointer vers n’importe quelle variable qui n’est pas déclaré avec le **const** ou `volatile` (mot clé). Un pointeur void ne peut pas être déréférencé, sauf s'il fait l'objet d'un cast en un autre type. Un pointeur void peut être converti en tout autre type de pointeur de données.  
  
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