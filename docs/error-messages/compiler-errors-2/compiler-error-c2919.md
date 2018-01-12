---
title: Erreur du compilateur C2919 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2919
dev_langs: C++
helpviewer_keywords: C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e2bde12c4c6ffa94f55e9dd205c3132a755ad94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2919"></a>Erreur du compilateur C2919
'type' : les opérateurs ne peuvent pas être utilisés sur la surface publiée d'un type WinRT  
  
 Le système de type Windows Runtime ne prend pas en charge les fonctions membres d'opérateur dans la surface publiée d'un type. Cela est dû au fait que tous les langages ne peuvent pas consommer les fonctions membres d'opérateur. Vous pouvez créer des fonctions membres d'opérateur privé ou interne qui peuvent être appelées à partir du code C++ dans la même unité de compilation ou de classe.  
  
 Pour résoudre ce problème, supprimez la fonction membre de l'opérateur à partir de l'interface publique, ou remplacez-la par une fonction membre nommée. Par exemple, à la place de `operator==`, nommez la fonction membre `Equals`.