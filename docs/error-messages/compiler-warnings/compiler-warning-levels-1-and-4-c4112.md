---
title: Compilateur avertissement (niveaux 1 et 4) C4112 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4112
dev_langs:
- C++
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e82b2425aef840d8da7a0d0ad4dc4b81bd2a812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>Avertissement du compilateur (niveaux 1 et 4) C4112
\#ligne nécessite un entier compris entre 1 et nombre  
  
 La directive [#line](../../preprocessor/hash-line-directive-c-cpp.md) spécifie un paramètre entier qui se trouve en dehors de la plage autorisée.  
  
 Si le paramètre spécifié est inférieur à 1, le compteur de lignes est réinitialisé à 1. Si le paramètre spécifié est supérieur à *nombre*, qui est la limite définie par le compilateur, le compteur de lignes est inchangé. Il s’agit d'un avertissement de niveau 1 sous compatibilité ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement de niveau 4 avec les extensions Microsoft ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 L’exemple suivant génère l’avertissement C4112 :  
  
```  
// C4112.cpp  
// compile with: /W4  
#line 0   // C4112, value must be between 1 and number  
  
int main() {  
}  
```