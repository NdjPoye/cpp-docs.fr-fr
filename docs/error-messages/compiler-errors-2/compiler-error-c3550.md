---
title: Erreur du compilateur C3550 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3550
dev_langs: C++
helpviewer_keywords: C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a05f0fc0b16cd7e3da851cb696f0ff60b8498319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3550"></a>Erreur du compilateur C3550
'decltype(auto)' simple est le seul autorisé dans ce contexte  
  
 Si `decltype(auto)` est utilisé comme espace réservé pour le type de retour d'une fonction, il doit être utilisé par lui-même. Il ne peut pas être utilisé dans le cadre d'une déclaration de pointeur (`decltype(auto*)`), d'une déclaration de référence (`decltype(auto&)`) ni de toute autre qualification de ce genre.  
  
## <a name="see-also"></a>Voir aussi  
 [auto](../../cpp/auto-cpp.md)