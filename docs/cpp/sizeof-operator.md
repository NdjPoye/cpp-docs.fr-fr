---
title: "sizeof, opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
- sizeof
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
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
ms.openlocfilehash: 67b699a93880a89e634ac024699ac79a9ea8d3ba
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="sizeof-operator"></a>sizeof, opérateur
Donne la taille de son opérande par rapport à la taille du type `char`.  
  
> [!NOTE]
>  Pour plus d’informations sur la `sizeof ...` (opérateur), consultez [Ellipses et modèles Variadiques](../cpp/ellipses-and-variadic-templates.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>Remarques  
 Le résultat de l'opérateur `sizeof` est de type `size_t`, un type intégral défini dans le fichier Include STDDEF.H. Cet opérateur vous permet d'éviter de spécifier les tailles de données dépendantes de l'ordinateur dans vos programmes.  
  
 L'opérande de `sizeof` peut être l'un des opérandes suivants :  
  
-   Un nom de type. Pour utiliser `sizeof` avec un nom de type, le nom doit être mis entre parenthèses.  
  
-   d'une expression. Quand il est utilisé avec une expression, `sizeof` peut être spécifié avec ou sans parenthèses. L'expression n'est pas évaluée.  
  
 Quand l'opérateur `sizeof` est appliqué à un objet de type `char`, il donne 1. Quand l'opérateur `sizeof` est appliqué à un tableau, il donne le nombre total d'octets dans ce tableau, et non la taille du pointeur représenté par l'identificateur du tableau. Pour obtenir la taille du pointeur représenté par l'identificateur du tableau, passez-le en tant que paramètre à une fonction utilisant `sizeof`. Exemple :  
  
## <a name="example"></a>Exemple  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 Quand l'opérateur `sizeof` est appliqué à un type `class`, `struct` ou `union`, le résultat est le nombre d'octets dans un objet de ce type, plus tout remplissage ajouté pour aligner les membres sur les limites de mots. Le résultat ne correspond pas forcément à la taille calculée en additionnant les exigences en matière de stockage des membres individuels. Le [/Zp](../build/reference/zp-struct-member-alignment.md) option du compilateur et la [pack](../preprocessor/pack.md) pragma affectent les limites d’alignement pour les membres.  
  
 L'opérateur `sizeof` ne donne jamais 0, même pour une classe vide.  
  
 L'opérateur `sizeof` ne peut pas être utilisé avec les opérandes suivants :  
  
-   Fonctions. (Toutefois, `sizeof` peut être appliqué aux pointeurs vers des fonctions.)  
  
-   Champ de bits.  
  
-   Classes indéfinies.  
  
-   Le type `void`.  
  
-   Tableaux alloués de manière dynamique.  
  
-   Tableaux externes.  
  
-   Types incomplets.  
  
-   Noms entre parenthèses de types incomplets.  
  
 Quand l'opérateur `sizeof` est appliqué à une référence, le résultat est le même que si `sizeof` est appliqué à l'objet lui-même.  
  
 Si un tableau non dimensionné est le dernier élément d'une structure, l'opérateur `sizeof` retourne la taille de la structure sans le tableau.  
  
 L'opérateur `sizeof` est souvent utilisé pour calculer le nombre d'éléments dans un tableau à l'aide de l'expression de forme :  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Mots clés](../cpp/keywords-cpp.md)
