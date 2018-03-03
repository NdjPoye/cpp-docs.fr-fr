---
title: "Évaluateur d’expression, erreur CXX0065 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0065
dev_langs:
- C++
helpviewer_keywords:
- CAN0065
- CXX0065
ms.assetid: aac68f87-0b90-4c19-afa6-1c587625a5fd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: db01baa10191df50c1f319bf8320263657088d75
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0065"></a>Évaluateur d'expression, erreur CXX0065
variable a besoin du frame de pile  
  
 Une expression contient une variable qui existe dans la portée actuelle, mais n’a pas encore été créée.  
  
 Cette erreur peut se produire lorsque vous avez exécuté le code dans le prologue d’une fonction, mais pas encore configurer le frame de pile pour la fonction, ou si vous avez exécuté le code dans le code de sortie pour la fonction.  
  
 Parcourez le code de prologue jusqu'à ce que le frame de pile a été configuré avant d’évaluer l’expression.  
  
 Cette erreur est identique à CAN0065.