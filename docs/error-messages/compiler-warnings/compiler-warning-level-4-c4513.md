---
title: Compilateur avertissement (niveau 4) C4513 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4513
dev_langs:
- C++
helpviewer_keywords:
- C4513
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c07828569b789c6035b5ea28d47d7fd026341026
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4513"></a>Avertissement du compilateur (niveau 4) C4513
'classe' : destructeur n’a pas pu être généré.  
  
 Le compilateur ne peut pas générer un destructeur par défaut pour la classe donnée ; aucun destructeur n’a été créé. Le destructeur est dans une classe de base qui n’est pas accessible à la classe dérivée. Si la classe de base a un destructeur privé, déclarez-le public ou protégé.