---
title: Compilateur avertissement (niveau 4) C4682 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4682
dev_langs:
- C++
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 076e8de6cbffa1f531cec875fd682a1daee42e74
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4682"></a>Avertissement du compilateur (niveau 4) C4682
'parameter' : aucun attribut de paramètre directionnel spécifié, [in] pris par défaut  
  
 Une méthode sur un paramètre dans une interface avec attributs ne possède pas l’un des attributs directionnels [in](../../windows/in-cpp.md) ou [out](../../windows/out-cpp.md). Le paramètre par défaut est in.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère l’avertissement C4682 :  
  
```  
// C4682.cpp  
// compile with: /W4  
#pragma warning(default : 4682)  
#include <windows.h>  
[module(name="MyModule")];  
  
[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]  
__interface IMyIface : IUnknown  
{  
   HRESULT f1(int i, int *pi); // C4682  
   // try the following line  
   // HRESULT f1([in] int i, [in] int *pi);  
};  
  
int main()  
{  
}  
```