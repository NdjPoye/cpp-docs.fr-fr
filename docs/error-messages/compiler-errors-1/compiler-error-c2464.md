---
title: Erreur du compilateur C2464 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2464
dev_langs:
- C++
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3992f1ecc19beb5c4fa1208fe82a93deab546260
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2464"></a>Erreur du compilateur C2464
'identificateur' : Impossible d’utiliser 'new' pour allouer une référence  
  
 Un identificateur de référence a été alloué avec la `new` opérateur. Références ne sont pas des objets de mémoire, par conséquent, `new` ne peut pas retourner un pointeur à ceux-ci. Utilisez la syntaxe de déclaration de variable standard pour déclarer une référence.  
  
 L’exemple suivant génère l’erreur C2464 :  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```