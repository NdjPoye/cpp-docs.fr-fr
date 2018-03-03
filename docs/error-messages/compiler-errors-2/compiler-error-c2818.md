---
title: Erreur du compilateur C2818 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f409acd9ba18972ca414c81cbcabd279e8903bcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2818"></a>Erreur du compilateur C2818
application de surchargé 'operator ->' est récurrente à travers le type 'type'  
  
 Une redéfinition de l’opérateur de l’accès de membre de classe contient une récursive `return` instruction. Pour redéfinir la `->` opérateur avec la récurrence, vous devez déplacer la routine récurrente vers une fonction appelée à partir de l’opérateur de substituer la fonction.