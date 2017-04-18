---
title: "C3390 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 257b0678ded15815f6673091d1adb26dea1dec12
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3390"></a>Erreur du compilateur C3390
'type_arg' : argument de type non valide pour le paramètre générique 'param' du générique 'generic_type', doit être un type référence  
  
Un type générique a été instancié de manière incorrecte.  Vérifiez la définition du type.  Pour plus d’informations, consultez [génériques](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
Le premier exemple utilise c# pour créer un composant qui contient un type générique qui comporte certaines contraintes qui ne sont pas pris en charge lors de la création de types génériques dans C++ / CLR. Pour plus d’informations, consultez [contraintes sur les paramètres de Type](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
Lorsque le composant C3390.dll est disponible, l’exemple suivant génère C3390.  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```
