---
title: Compilateur avertissement (niveau 1) C4508 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4508
dev_langs: C++
helpviewer_keywords: C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52139327831be17d6800f30b00f667da7d3b0376
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4508"></a>Avertissement du compilateur (niveau 1) C4508
'fonction' : fonction doit retourner une valeur ; 'void' pris par défaut de type de retour  
  
 La fonction n’a aucun type de retour spécifié. Dans ce cas, C4430 doit également déclencher et le compilateur implémente le correctif signalé par l’erreur C4430 (valeur par défaut est de type int).  
  
 Pour résoudre cet avertissement, déclarer explicitement le type de retour des fonctions.  
  
 L’exemple suivant génère C4508 :  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```