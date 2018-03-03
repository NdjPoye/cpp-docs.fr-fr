---
title: Compilateur avertissement (niveau 1) C4692 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4692
dev_langs:
- C++
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8088c1434ab33899f60b08c0817464f9ddb9c82e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4692"></a>Avertissement du compilateur (niveau 1) C4692
'fonction' : la signature de membre non privée contient un type natif privé d'assembly 'type_natif'  
  
 Un type qui est visible en dehors de l’assembly contient une fonction membre dont la signature contient un type natif qui n’est pas visible à l’extérieur de l’assembly. Par conséquent, la fonction membre ne doit pas être appelée si son type conteneur est instancié en dehors de l’assembly.  
  
 Pour plus d’informations, consultez [visibilité de Type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).  
  
 Cet avertissement est désactivé par défaut. Pour plus d'informations, consultez [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4692.  
  
```  
// C4692.cpp  
// compile with: /W1 /c /clr  
#pragma warning(default:4692)  
class Private_Native_Class {};  
public class Public_Native_Class {};  
public ref class Public_Ref_Class {  
public:  
   void Test(Private_Native_Class *) {}   // C4692  
   void Test2(Public_Native_Class *) {}   // OK  
};  
```