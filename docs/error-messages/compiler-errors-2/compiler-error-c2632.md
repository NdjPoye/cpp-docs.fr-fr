---
title: Erreur du compilateur C2632 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2632
dev_langs: C++
helpviewer_keywords: C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03a6d75ab9af6cd45ef982ff9d2e12640266c1b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2632"></a>Erreur du compilateur C2632
'type1' suivi de 'type2' est non conforme  
  
 Cette erreur peut être provoquée si le code entre deux spécificateurs de type est manquant.  
  
 L’exemple suivant génère C2632 :  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual Studio .NET 2003. `bool`est maintenant un type approprié. Dans les versions précédentes, `bool` était un typedef et vous pouviez créer des identificateurs portant ce nom.  
  
 L’exemple suivant génère C2632 :  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 Pour résoudre cette erreur, afin que le code soit valide dans les versions de Visual Studio .NET 2003 et de Visual Studio .NET de Visual C++, renommez l’identificateur.