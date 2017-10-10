---
title: Erreur du compilateur C2834 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5b85b01fa832b0d14d01b6b7cbb5ef65107177ef
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2834"></a>Erreur du compilateur C2834
'operator opérateur' doit être globalement qualifié  
  
 Le `new` et `delete` opérateurs sont liés à la classe où elles résident. Résolution de portée ne peut pas être utilisée pour sélectionner une version de `new` ou `delete` à partir d’une autre classe. Pour implémenter plusieurs formes de le `new` ou `delete` (opérateur), créez une version de l’opérateur avec des paramètres formels supplémentaires.
