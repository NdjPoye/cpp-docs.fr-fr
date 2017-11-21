---
title: Compilateur avertissement (niveau 1) C4377 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e52479aac07cdb31f62b20cb6c865b48b270c2bb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4377"></a>Avertissement du compilateur (niveau 1) C4377
les types natifs sont privés par défaut ; -d1PrivateNativeTypes est déconseillé.  
  
 Dans les versions précédentes, les types natifs dans les assemblys étaient publics par défaut et une option de compilateur interne, non documentée (**/d1PrivateNativeTypes**) a été utilisé pour les rendre privé.  
  
 Tous les types, natifs et CLR, sont désormais privés par défaut dans un assembly, donc **/d1PrivateNativeTypes** n’est plus nécessaire.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4377.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```