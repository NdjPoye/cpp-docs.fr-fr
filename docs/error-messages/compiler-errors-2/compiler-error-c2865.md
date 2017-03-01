---
title: Erreur du compilateur C2865 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 3bb55d094e00400c57617857aa1ac29677f1b72a
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2865"></a>Erreur du compilateur C2865
'fonction' : comparaison non conforme pour handle_ou_pointeur  
  
 Vous pouvez comparer les références aux [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md) ou gérés par les types de référence uniquement pour l’égalité pour voir s’ils font référence au même objet (==) ou à des objets différents ( ! =).  
  
 Vous ne peut pas les comparer pour les trier car le runtime .NET peut déplacer les objets managés à tout moment, modifier le résultat du test.
