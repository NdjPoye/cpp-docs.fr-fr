---
title: Compilateur avertissement (niveau 4) C4057 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4057
dev_langs:
- C++
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c9ef5041d26e2e5a8933a53d4f6f0153c7106cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4057"></a>Avertissement du compilateur (niveau 4) C4057
'opérateur' : 'identificateur1' diffère de 'identificateur2' dans l’indirection vers des types de base légèrement différents  
  
 Deux expressions de pointeur font référence à des types de base différents. Les expressions sont utilisées sans conversion.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Mélange de types signés et non signés.  
  
2.  Mélange de types **short** et **long** .