---
title: Erreur du compilateur C3744 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3744
dev_langs:
- C++
helpviewer_keywords:
- C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd5c11e88960f2b4332a586d2fe982a8ea94fdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3744"></a>Erreur du compilateur C3744
__unhook doit avoir au moins 3 arguments pour les événements managés  
  
 Le [__unhook](../../cpp/unhook.md) fonction doit prendre trois paramètres lorsqu’il est utilisé dans un programme qui est compilé pour les Extensions managées pour C++.  
  
 `__hook`et `__unhook` ne sont pas compatibles avec la programmation /clr. Utilisez les opérateurs += et -= à la place.  
  
 C3744 est uniquement accessible à l’aide de l’option du compilateur obsolète **oldSyntax ;**.  
