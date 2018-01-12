---
title: "Du compilateur (niveau 1) d’avertissement C4190 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4190
dev_langs: C++
helpviewer_keywords: C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 127eb4327826412d605f2a4a008e411880998073
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4190"></a>Du compilateur (niveau 1) d’avertissement C4190
'identificateur1' a une liaison C spécifiée, mais retourne UDT 'identificateur2' qui est incompatible avec C  
  
 Une fonction ou un pointeur vers une fonction a un type UDT (user defined type, classe, structure, enum ou union) en tant que type de retour et `extern` une liaison de « C ». Cela est légal si :  
  
-   Tous les appels à cette fonction se produisent à partir de C++.  
  
-   La définition de la fonction est en C++.  
  
## <a name="example"></a>Exemple  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```