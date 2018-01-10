---
title: Erreur du compilateur C3622 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3622
dev_langs: C++
helpviewer_keywords: C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75d853b01f4f88fbf5e435b3b1f7a86fed0c8388
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3622"></a>Erreur du compilateur C3622
'classe' : une classe déclarée comme 'mot_clé' ne peut pas être instanciée.  
  
Une tentative a été effectuée pour instancier une classe marquée en tant que [abstraite](../../windows/abstract-cpp-component-extensions.md). Une classe marquée en tant que `abstract` peut être une classe de base, mais elle ne peut pas être instanciée.  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère C3622.  
  
```  
// C3622.cpp  
// compile with: /clr  
ref class a abstract {};  
  
int main() {  
   a aa;   // C3622  
}  
```  
