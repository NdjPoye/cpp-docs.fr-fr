---
title: Erreur du compilateur C3715 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3715
dev_langs:
- C++
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0fcfe83ada2c55540562fc17189d693675326c81
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3715"></a>Erreur du compilateur C3715
'pointeur' : doit être un pointeur vers 'class'  
  
 Vous avez spécifié un pointeur dans [__hook](../../cpp/hook.md) ou [__unhook](../../cpp/unhook.md) qui ne pointe pas vers une classe valide. Pour corriger cette erreur, assurez-vous que votre `__hook` et `__unhook` appels spécifient des pointeurs vers des classes valides.
