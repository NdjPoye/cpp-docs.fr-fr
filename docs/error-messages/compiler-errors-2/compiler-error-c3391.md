---
title: Erreur du compilateur C3391 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3391
dev_langs:
- C++
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28615d85eca534966a4d8b90cef20ea577e0d592
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3391"></a>Erreur du compilateur C3391
'arg_type' : argument de type non valide pour le paramètre générique 'param' du générique 'type_générique', doit être un type valeur non nullable  
  
Un type générique a été instancié de manière incorrecte. Vérifiez la définition du type. Pour plus d’informations, consultez <xref:System.Nullable> et [génériques](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
L’exemple suivant utilise c# pour créer un composant qui contient un type générique qui a certaines contraintes qui ne sont pas pris en charge lors de la création de types génériques dans le langage c++ / CLI. Pour plus d’informations, consultez [Contraintes sur les paramètres de type](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3391.cs  
// Compile by using: csc /target:library C3391.cs  
// a C# program  
public class GR<N>  
where N : struct {}  
```  
  
Lorsque le composant C3391.dll est disponible, l’exemple suivant génère l’erreur C3391.  
  
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