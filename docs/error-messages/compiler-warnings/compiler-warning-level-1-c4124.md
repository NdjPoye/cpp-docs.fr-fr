---
title: Compilateur avertissement (niveau 1) C4124 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38588fb242b5b4167984e15d101594d1b015ec86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4124"></a>Compilateur avertissement (niveau 1) C4124
__fastcall avec contrôle de pile est inefficace  
  
 Le `__fastcall` mot clé a été utilisé avec le contrôle de pile activé.  
  
 Le `__fastcall` convention génère du code plus rapide, mais la vérification de la pile de rend le code plus lent. Lorsque vous utilisez `__fastcall`, désactiver la vérification de la pile avec les **check_stack** pragma ou/GS.  
  
 Cet avertissement est émis uniquement pour la première fonction déclarée dans ces conditions.