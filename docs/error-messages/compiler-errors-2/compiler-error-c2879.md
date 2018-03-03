---
title: Erreur du compilateur C2879 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4de37b504d32eabbd97dcb2f4fbbafc82841f713
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2879"></a>Erreur du compilateur C2879
'symbole' : seul un espace de noms existant peut être renommé par une définition d’alias d’espace de noms  
  
 Vous ne pouvez pas créer un [alias d’espace de noms](../../cpp/namespaces-cpp.md#namespace_aliases) à un symbole autre qu’un espace de noms.  
  
 L’exemple suivant génère l’erreur C2879 :  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```