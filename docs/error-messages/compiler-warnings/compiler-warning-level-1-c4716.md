---
title: Compilateur avertissement (niveau 1) C4716 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4716
dev_langs:
- C++
helpviewer_keywords:
- C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a1d9d1e91656e464a5af809f1559eddba5da3291
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4716"></a>Avertissement du compilateur (niveau 1) C4716
'fonction' doit retourner une valeur  
  
 La fonction donnée n’a pas retourné une valeur.  
  
 Fonctionne uniquement avec un type de retour void peuvent utiliser la commande return sans valeur de retour associée.  
  
 Une valeur non définie s’affichera lorsque cette fonction est appelée.  
  
 Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md).  
  
 L’exemple suivant génère C4716 :  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```