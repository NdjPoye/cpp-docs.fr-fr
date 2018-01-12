---
title: Compilateur avertissement (niveau 1) C4216 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4216
dev_langs: C++
helpviewer_keywords: C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e036b27972965aee85c05b987932206d52c030fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4216"></a>Avertissement du compilateur (niveau 4) C4216
extension non standard utilisée : float long  
  
 Les valeur par défaut les extensions Microsoft (/Ze) traitent **float long** en tant que **double**. La compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) n’est pas. Utilisez **double** pour assurer la compatibilité. L’exemple suivant génère l’erreur C4216 :  
  
```  
// C4216.cpp  
// compile with: /W1  
float long a;   // C4216  
  
// use the line below to resolve the warning  
// double a;  
  
int main() {  
}  
```