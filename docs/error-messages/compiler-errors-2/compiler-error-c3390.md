---
title: Erreur du compilateur C3390 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea23a13a338e5d09eac0714914d9c1020b5908cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3390"></a>Erreur du compilateur C3390
'type_arg' : argument de type non valide pour le paramètre générique 'param' du générique 'generic_type', doit être un type référence  
  
Un type générique a été instancié de manière incorrecte.  Vérifiez la définition du type.  Pour plus d’informations, consultez la page [Génériques](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
Le premier exemple utilise c# pour créer un composant qui contient un type générique qui a certaines contraintes qui ne sont pas pris en charge lors de la création de types génériques dans le langage c++ / CLR. Pour plus d’informations, consultez [Contraintes sur les paramètres de type](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
Lorsque le composant C3390.dll est disponible, l’exemple suivant génère l’erreur C3390.  
  
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