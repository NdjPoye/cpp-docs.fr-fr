---
title: Erreur du compilateur C3399 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3399
dev_langs:
- C++
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a55a6d40d6d39b368c31a2716c14d05e0e49a78c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3399"></a>Erreur du compilateur C3399
'type' : impossible de fournir des arguments lors de la création d’une instance d’un paramètre générique  
  
 Quand vous spécifiez la contrainte `gcnew()` , vous indiquez que le type de contrainte aura un constructeur sans paramètre. Il est donc incorrect d’essayer d’instancier ce type et de passer un paramètre.  
  
 Consultez [contraintes sur les paramètres de Type générique (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3399.  
  
```  
// C3399.cpp  
// compile with: /clr /c  
generic <class T>   
where T : gcnew()  
void f() {  
   T t = gcnew T(1);   // C3399  
   T t2 = gcnew T();   // OK  
}  
```