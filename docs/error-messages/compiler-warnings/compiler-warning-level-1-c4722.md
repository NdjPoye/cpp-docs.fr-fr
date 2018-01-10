---
title: Compilateur avertissement (niveau 1) C4722 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4722
dev_langs: C++
helpviewer_keywords: C4722
ms.assetid: d8660710-f67b-4f59-a5fd-59259475529e
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97c9dff3044eda5ea04bd41a9fda81b5f1af4f13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4722"></a>Avertissement du compilateur (niveau 1) C4722
'fonction' : aucun retour du destructeur, fuite de mémoire possible  
  
 Le flux de contrôle se termine dans un destructeur. Le thread ou la totalité du programme va se terminer et les ressources allouées risquent de ne pas être libérées.  En outre, si un destructeur est appelé pour le déroulement de pile pendant le traitement de l’exception, le comportement du fichier exécutable est indéfini.  
  
 Pour résoudre ce problème, supprimez l’appel de fonction qui provoque le non-retour du destructeur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4722 :  
  
```  
// C4722.cpp  
// compile with: /O1 /W1 /c  
#include <stdlib.h>  
class C {  
public:  
   C();  
   ~C() { exit(1); };   // C4722  
};  
  
extern void func (C*);  
  
void Test(){  
   C x;  
   func(&x);  
   // control will not leave Test because destructor will exit  
}  
```