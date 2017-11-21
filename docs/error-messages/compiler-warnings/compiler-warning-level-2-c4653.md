---
title: Compilateur avertissement (niveau 2) C4653 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4653
dev_langs: C++
helpviewer_keywords: C4653
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 627039bdebc0f339ea09c144967356b7e288c2ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4653"></a>Avertissement du compilateur (niveau 2) C4653
option du compilateur 'option' non cohérente avec l’en-tête précompilé ; option de ligne de commande en cours ignorée  
  
 Une option spécifiée avec l’utiliser des en-têtes précompilés ([/Yu](../../build/reference/yu-use-precompiled-header-file.md)) option était incompatible avec les options spécifiées lors de la création de l’en-tête précompilé. Cette compilation a utilisé l’option spécifiée lors de la création de l’en-tête précompilé.  
  
 Cet avertissement peut se produire lorsqu’une valeur différente de l’option Pack Structures ([/Zp](../../build/reference/zp-struct-member-alignment.md)) a été spécifiée pendant la compilation de l’en-tête précompilé.