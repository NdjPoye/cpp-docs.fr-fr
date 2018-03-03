---
title: Erreur du compilateur C2482 | Documents Microsoft
ms.custom: 
ms.date: 09/15/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4a5d081e7a19f09f10e40e3799f724f44b295fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2482"></a>Erreur du compilateur C2482

>'*identificateur*' : l’initialisation dynamique de données 'thread' non autorisée

Ce message d’erreur est obsolète dans Visual Studio 2015 et versions ultérieures. Dans les versions précédentes, les variables déclarées à l’aide de la `thread` attribut ne peut pas être initialisé avec une expression qui requiert une évaluation de l’exécution. Une expression statique est requise pour initialiser `thread` données.

## <a name="example"></a>Exemple

L’exemple suivant génère l’erreur C2482 dans Visual Studio 2013 et versions antérieures :

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
