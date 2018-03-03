---
title: Compilateur avertissement (niveau 1) C4917 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4917
dev_langs:
- C++
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 37849850c89f8c02726b730fbdbabed66bd849b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4917"></a>Avertissement du compilateur (niveau 1) C4917
'déclarateur' : un GUID ne peut être associé à une classe, d’interface ou espace de noms  
  
Une structure définie par l’utilisateur autres que [classe](../../cpp/class-cpp.md), [interface](../../cpp/interface.md), ou [espace de noms](../../cpp/namespaces-cpp.md) ne peut pas avoir un GUID.  
  
Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
## <a name="example"></a>Exemple  
L’exemple de code suivant génère C4917 :  
  
```cpp  
// C4917.cpp  
// compile with: /W1  
#pragma warning(default : 4917)  
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S  
{  
} s;   // C4917, don't put uuid on a struct  
  
int main()  
{  
}  
```