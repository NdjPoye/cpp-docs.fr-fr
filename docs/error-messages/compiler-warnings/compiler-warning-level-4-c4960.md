---
title: Compilateur avertissement (niveau 4) C4960 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4960
dev_langs:
- C++
helpviewer_keywords:
- C4960
ms.assetid: 3b4ed286-9e8d-46f1-af0c-00ba669693a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1281bc86ad363c02df5c39ed41f616a6fff1a9b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4960"></a>Avertissement du compilateur (niveau 4) C4960
'function' est trop grand pour être profilé  
  
 Quand vous avez utilisé [/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un module d’entrée avec une fonction comprenant plus de 65 535 instructions. Une fonction de cette taille n’est pas disponible pour les optimisations guidées par profil.  
  
 Pour résoudre cet avertissement, réduisez la taille de la fonction.