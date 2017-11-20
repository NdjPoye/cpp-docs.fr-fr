---
title: Compilateur avertissement (niveau 1) C4445 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4445
dev_langs: C++
helpviewer_keywords: C4445
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c31e9fa08b5aad05fef8af64f29eb75bc136e0f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4445"></a>Avertissement du compilateur (niveau 1) C4445
'fonction' : dans un type WinRT ou managé, une méthode virtuelle ne peut pas être privée  
  
 Si une fonction virtuelle est privée, un type dérivé ne peut pas y accéder. Pour corriger cette erreur, modifiez l'accessibilité de la fonction membre virtuelle pour qu'elle soit protégée ou publique.