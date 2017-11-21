---
title: Erreur du compilateur C3744 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3744
dev_langs: C++
helpviewer_keywords: C3744
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 87df3fd92ac3fcad9b3e87f02f16b8151e678b77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3744"></a>Erreur du compilateur C3744
__unhook doit avoir au moins 3 arguments pour les événements managés  
  
 Le [__unhook](../../cpp/unhook.md) fonction doit prendre trois paramètres lorsqu’il est utilisé dans un programme qui est compilé pour les Extensions managées pour C++.  
  
 `__hook`et `__unhook` ne sont pas compatibles avec la programmation /clr. Utilisez les opérateurs += et -= à la place.  
  
 C3744 est uniquement accessible à l’aide de l’option du compilateur obsolète **oldSyntax ;**.  
