---
title: "Arguments de fonction de Type référence | Documents Microsoft"
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
- arguments [C++], function
- functions [C++], paramters
- function parameters, reference-type
- function arguments, reference-type
- passing parameters, reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
caps.latest.revision: 8
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
ms.openlocfilehash: e74cbde44cad618720983fbda4a6cf9ce8b75dc1
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="reference-type-function-arguments"></a>Arguments de fonction de type référence
Il est souvent plus efficace de passer des références que de grands objets à des fonctions. Cela permet au compilateur de passer l'adresse de l'objet tout en maintenant la syntaxe qui aurait été utilisée pour accéder à l'objet. Prenons l'exemple suivant, qui utilise la structure `Date` :  
  
```  
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 Le code précédent montre que les membres d’une structure passée par référence sont accessibles à l’aide de l’opérateur de sélection de membre (**.**) au lieu de l’opérateur de sélection de membre pointeur (**->**).  
  
 Bien que les arguments passés comme types référence observent la syntaxe des types non-pointeur, ils conservent une fonctionnalité importante des types pointeur : ils sont modifiables, sauf si déclarée en tant que **const**. Comme l'objectif du code précédent n'est pas de modifier l'objet `GDate`, un prototype de fonction plus approprié est :  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Ce prototype garantit que la fonction `JulianFromGregorian` ne modifiera pas son argument.  
  
 Toute fonction prototypée comme acceptant un type référence peut accepter un objet du même type à la place, car il existe une conversion standard de *typename* à *typename* ** & **.  
  
## <a name="see-also"></a>Voir aussi  
 [Références](../cpp/references-cpp.md)
