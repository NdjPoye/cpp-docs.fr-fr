---
title: Compilateur avertissement (niveau 1) C4052 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4052
dev_langs: C++
helpviewer_keywords: C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 24be11296f5a79569dd02bbabafc765527ce1a40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4052"></a>Avertissement du compilateur (niveau 1) C4052
déclarations de fonction différentes, une seule contient des arguments de variables  
  
 L’une des déclarations de la fonction ne contient pas d’arguments de variables. Elle est ignorée.  
  
 L’exemple suivant génère l’avertissement C4052 :  
  
```  
// C4052.c  
// compile with: /W4 /c  
int f();  
int f(int i, ...);   // C4052  
```