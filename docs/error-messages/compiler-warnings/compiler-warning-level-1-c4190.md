---
title: Compilateur avertissement (niveau 1) C4190 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf45c0737f52da93f93c1f95d313771f0e92a10e
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4190"></a>Compilateur avertissement (niveau 1) C4190
« identifier1 » a une liaison C spécifiée, mais retourne UDT 'identificateur2' qui est incompatible avec C  
  
 Une fonction ou un pointeur vers une fonction a un UDT (défini par l’utilisateur type, classe, structure, enum ou union) comme type de retour et `extern` une liaison « C ». Cela est légal si :  
  
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
