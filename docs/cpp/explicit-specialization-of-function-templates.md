---
title: "Spécialisation explicite des modèles de fonction | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, functions
- function templates, specialization
- explicit specialization of function templates
- declaring functions [C++], specialization of function template
- specialization of function templates
ms.assetid: eb0fcb73-eaed-42a1-9b83-14b055a34bf8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f460497071445cff87308fa9bf6e0d43c6f13a3e
ms.openlocfilehash: c5caabae41383edbdc92806249026ce8a0daa5d5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-specialization-of-function-templates"></a>Spécialisation explicite de modèles de fonctions
Avec un modèle de fonction, vous pouvez définir un comportement spécial pour un type spécifique en fournissant une spécialisation explicite (substitution) du modèle de fonction pour ce type. Exemple :  
  
```cpp
template<> void MySwap(double a, double b);  
```  
  
 Cette déclaration vous permet de définir une fonction différente pour **double** variables. Comme les fonctions sans modèle, les conversions de types standard (telles que la promotion d’une variable de type **float** à **double**) sont appliquées.  
  
## <a name="example"></a>Exemple  
  
```cpp
// explicit_specialization.cpp  
template<class T> void f(T t)  
{  
};  
  
// Explicit specialization of f with 'char' with the  
// template argument explicitly specified:  
//  
template<> void f<char>(char c)  
{  
}  
  
// Explicit specialization of f with 'double' with the  
// template argument deduced:  
//  
template<> void f(double d)  
{  
}  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)

