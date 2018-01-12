---
title: Erreur du compilateur C2410 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2410
dev_langs: C++
helpviewer_keywords: C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3cd5dfa7b33f5af5c57f6479170a7a56df39a0e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2410"></a>Erreur du compilateur C2410
'identificateur' : nom de membre ambigu dans 'contexte'  
  
 L’identificateur est un membre de plus d’une structure ou union dans ce contexte.  
  
 Utilisez un spécificateur d’union ou de structure sur l’opérande qui a provoqué l’erreur. Un spécificateur d’union ou de structure est un identificateur de type `struct` ou `union` (un `typedef` nom ou une variable du même type que la structure ou l’union référencée). Le spécificateur doit être l’opérande gauche du premier opérateur de sélection de membres (.) pour utiliser l’opérande.