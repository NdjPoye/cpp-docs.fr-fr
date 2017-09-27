---
title: try, throw et catch instructions (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- catch_cpp
- throw
- try_cpp
- try
- throw_cpp
- catch
dev_langs:
- C++
helpviewer_keywords:
- catch keyword [C++]
- keywords [C++], exception handling
- C++ exception handling, statement syntax
- try-catch keyword [C++], about try-catch exception handling
- throw keyword [C++]
- try-catch keyword [C++]
- try-catch keyword [C++], exception handling
- throwing exceptions, throw keyword
- try-catch keyword [C++], throw keyword [C++]s
- throwing exceptions, implementing C++ exception handling
- throwing exceptions
- throw keyword [C++], throw() vs. throw(...)
ms.assetid: 15e6a87b-b8a5-4032-a7ef-946c644ba12a
caps.latest.revision: 24
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
ms.openlocfilehash: 89db418a92239460379d1ea41d2d49a8073095c2
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="try-throw-and-catch-statements-c"></a>Instructions try, throw et catch (C++)
Pour implémenter la gestion des exceptions dans C++, utilisez les expressions `try`, `throw` et `catch`.  
  
 Utilisez d'abord un bloc `try` pour englober une ou plusieurs instructions susceptibles de lever une exception.  
  
 Une expression `throw` indique qu'une condition exceptionnelle, souvent une erreur, s'est produite dans un bloc `try`. Vous pouvez utiliser un objet de n'importe quel type comme opérande d'une expression `throw`. En général, cet objet est utilisé pour transmettre des informations sur l'erreur. Dans la plupart des cas, nous vous recommandons d’utiliser le [std::exception](../standard-library/exception-class.md) classe ou l’une des classes dérivées qui sont définis dans la bibliothèque standard. Si l'une de celles-ci est inadéquate, nous vous recommandons de dériver votre propre classe d'exceptions de `std::exception`.  
  
 Pour gérer les exceptions qui peuvent être levées, implémentez un ou plusieurs blocs `catch` immédiatement après un bloc `try`. Chaque bloc `catch` spécifie le type d'exception qu'il peut gérer.  
  
 Cet exemple montre un bloc `try` et ses gestionnaires. Supposons que `GetNetworkResource()` acquiert des données via une connexion réseau et que les deux types d'exception sont des classes définies par l'utilisateur qui dérivent de `std::exception`. Notez que les exceptions sont interceptées par référence à `const` dans l'instruction `catch`. Nous vous recommandons de lever des exceptions par valeur et de les intercepter par référence const.  
  
## <a name="example"></a>Exemple  
  
```  
  
MyData md;  
try {  
   // Code that could throw an exception  
   md = GetNetworkResource();  
}  
catch (const networkIOException& e) {  
   // Code that executes when an exception of type  
   // networkIOException is thrown in the try block  
   // ...  
   // Log error message in the exception object  
   cerr << e.what();  
}  
catch (const myDataFormatException& e) {  
   // Code that handles another exception type  
   // ...  
   cerr << e.what();  
}  
  
// The following syntax shows a throw expression  
MyData GetNetworkResource()  
{  
   // ...  
   if (IOSuccess == false)  
      throw networkIOException("Unable to connect");  
   // ...  
   if (readError)  
      throw myDataFormatException("Format error");   
   // ...  
}  
```  
  
## <a name="remarks"></a>Remarques  
 Le code suivant la clause `try` représente la section protégée du code. Le `throw` expression *lève*: autrement dit, déclenche : une exception. Le bloc de code après la clause `catch` constitue le gestionnaire d'exceptions. Il s’agit du gestionnaire qui *intercepte* l’exception est levée si les types dans les `throw` et `catch` expressions sont compatibles. Pour obtenir la liste des règles qui régissent la mise en correspondance de type dans `catch` blocs, consultez [comment les blocs Catch sont évalués](../cpp/how-catch-blocks-are-evaluated-cpp.md). Si l'instruction `catch` spécifie des points de suspension (...) au lieu d'un type, le bloc `catch` gère chaque type d'exception. Lorsque vous compilez avec le [/EHa](../build/reference/eh-exception-handling-model.md) option, celles-ci peuvent inclure des exceptions structurées par C et des exceptions asynchrones générées par le système ou générés par l’application telles que des violations de division par zéro et à virgule flottante de protection, de mémoire . Les blocs `catch` étant traités dans l'ordre du programme pour trouver un type correspondant, le gestionnaire de points de suspension devra être le dernier gestionnaire associé au bloc `try`. Utilisez `catch(...)` avec précaution ; n'autorisez pas un programme à continuer sans que le bloc catch sache comment gérer l'exception spécifique qui est interceptée. En général, un bloc `catch(...)` est utilisé pour enregistrer des erreurs et effectuer un nettoyage spécial avant l'arrêt de l'exécution du programme.  
  
 Une expression `throw` sans opérande lève à nouveau l'exception en cours de traitement. Nous recommandons ce format lorsqu'une exception est levée à nouveau, car celui-ci préserve les informations de type polymorphe de l'exception d'origine. Une telle expression doit être utilisée uniquement dans un gestionnaire `catch` ou dans une fonction appelée depuis un gestionnaire `catch`. L'objet d'une exception levée à nouveau est l'objet de l'exception d'origine, pas une copie.  
  
```  
try {  
   throw CSomeOtherException();  
}  
catch(...) {  
   // Catch all exceptions - dangerous!!!  
   // Respond (perhaps only partially) to the exception, then  
   // re-throw to pass the exception to some other handler  
   // ...  
   throw;  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion des exceptions C++](../cpp/cpp-exception-handling.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 [Exceptions C++ non gérées](../cpp/unhandled-cpp-exceptions.md)   
 [__uncaught_exception](../c-runtime-library/reference/uncaught-exception.md)
