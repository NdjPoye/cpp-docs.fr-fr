---
title: Erreur du compilateur C3798 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3798
dev_langs:
- C++
helpviewer_keywords:
- C3798
ms.assetid: b2f8b1d8-8812-49b8-a346-28e48f02ba5c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da4ca81f2110ff1f76fdc9d0377234087a532017
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3798"></a>Erreur du compilateur C3798
'spécificateur' : déclaration de propriété ne peut pas avoir de spécificateur de substitution (doit être placé sur la propriété méthodes get/set à la place)  
  
 Une propriété n’a pas été correctement déclarée. Pour plus d'informations, consultez  
  
-   [propriété](../../windows/property-cpp-component-extensions.md)  
  
-   [abstract](../../windows/abstract-cpp-component-extensions.md)  
  
-   [sealed](../../windows/sealed-cpp-component-extensions.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3798  
  
```  
// C3798.cpp  
// compile with: /clr /c  
ref struct A {  
   property int Prop_1 abstract;   // C3798  
   property int Prop_2 sealed;   // C3798  
  
   // OK  
   property int Prop_3 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
  
   property int Prop_4 {  
      virtual int get() sealed;  
      virtual void set(int i) sealed;  
   }  
};  
```