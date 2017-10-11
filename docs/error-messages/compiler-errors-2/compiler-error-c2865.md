---
title: Erreur du compilateur C2865 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5cbe54ebcae8753c0c5b6701ca839202ba7da533
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2865"></a>Erreur du compilateur C2865
'fonction' : comparaison non conforme pour handle_ou_pointeur  
  
 Vous pouvez comparer les références aux [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md) ou gestion des types de référence uniquement pour l’égalité pour voir s’ils font référence au même objet (==) ou à des objets différents ( ! =).  
  
 Impossible de comparer les pour le classement car le runtime .NET peut déplacer des objets managés à tout moment, modifier le résultat du test.
