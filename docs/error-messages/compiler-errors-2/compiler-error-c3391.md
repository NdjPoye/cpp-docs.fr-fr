---
title: "C3391 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
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
ms.openlocfilehash: 7b5922ccf353162dc32c99e3818227639d0f5985
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3391"></a>Erreur du compilateur C3391
'arg_type' : argument de type non valide pour le paramètre générique 'param' du générique 'type_générique', doit être un type valeur non nullable  
  
Un type générique a été instancié de manière incorrecte. Vérifiez la définition du type. Pour plus d’informations, consultez <xref:System.Nullable>et [génériques](../../windows/generics-cpp-component-extensions.md).</xref:System.Nullable>  
  
## <a name="example"></a>Exemple  
L’exemple suivant utilise c# pour créer un composant qui contient un type générique qui comporte certaines contraintes qui ne sont pas pris en charge lors de la création de types génériques dans C++ / CLI. Pour plus d’informations, consultez [contraintes sur les paramètres de Type](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
Lorsque le composant C3391.dll est disponible, l’exemple suivant génère C3391.  
  
```cpp  
// C3391_b.cpp  
// Compile by using: cl /clr C3391_b.cpp  
#using <C3391.dll>  
using namespace System;  
value class VClass {};  
  
int main() {  
   GR< Nullable<VClass> >^ a =   
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable  
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK  
}  
```
