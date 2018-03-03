---
title: Erreur du compilateur C3753 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3753
dev_langs:
- C++
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f68e4fb49116418377235a283eadbf2f28e92885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3753"></a>Erreur du compilateur C3753
une propriété générique n’est pas autorisée.  
  
 Listes de paramètres génériques peuvent uniquement apparaître sur les classes managées, des structures ou fonctions.  
  
 Pour plus d’informations, consultez [génériques](../../windows/generics-cpp-component-extensions.md) et [propriété](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3753.  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```