---
title: Erreur du compilateur C2410 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2410
dev_langs:
- C++
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d2f8f9b21d44c2fce92c526de0f6d53b99930b8
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2410"></a>Erreur du compilateur C2410
'identificateur' : nom de membre ambigu dans 'contexte'  
  
 L’identificateur est un membre de plus d’une structure ou union dans ce contexte.  
  
 Utilisez un spécificateur d’union ou de structure sur l’opérande qui a provoqué l’erreur. Un spécificateur d’union ou de structure est un identificateur de type `struct` ou `union` (un `typedef` nom ou une variable du même type que la structure ou l’union référencée). Le spécificateur doit être l’opérande gauche du premier opérateur de sélection de membres (.) pour utiliser l’opérande.
