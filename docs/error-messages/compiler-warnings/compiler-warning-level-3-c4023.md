---
title: Compilateur avertissement (niveau 3) C4023 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 213d72e39575b447787c3e0ead7910baedc8e815
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4023"></a>Avertissement du compilateur (niveau 3) C4023
'symbole' : pointeur based passé à une fonction non prototypée : paramètre nombre  
  
 Passer un pointeur based à une fonction non prototypée entraîne la normalisation du pointeur, avec des résultats imprévisibles.  
  
 Vous pouvez résoudre cet avertissement en utilisant des fonctions prototypées auxquelles sont passées des pointeurs based.