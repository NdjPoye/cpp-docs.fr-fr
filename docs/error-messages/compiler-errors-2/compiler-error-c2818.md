---
title: Erreur du compilateur C2818 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2818
dev_langs: C++
helpviewer_keywords: C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 02c1b8e67679e7b8ce69b202c3ddef899439095d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2818"></a>Erreur du compilateur C2818
application de surchargé 'operator ->' est récurrente à travers le type 'type'  
  
 Une redéfinition de l’opérateur de l’accès de membre de classe contient une récursive `return` instruction. Pour redéfinir la `->` opérateur avec la récurrence, vous devez déplacer la routine récurrente vers une fonction appelée à partir de l’opérateur de substituer la fonction.