---
title: Compilateur avertissement (niveau 3) C4278 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 249b13b70f3f10942852d7a9aa13dcf4f08e1f7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4278"></a>Avertissement du compilateur (niveau 3) C4278
'identificateur' : identificateur de la bibliothèque de types 'tlb' est déjà une macro ; Utilisez le qualificateur 'rename'  
  
 Lorsque vous utilisez [#import](../../preprocessor/hash-import-directive-cpp.md), un identificateur dans la bibliothèque de types que vous importez tente de déclarer un identificateur ***identificateur***. Toutefois, il est déjà un symbole valide.  
  
 Utilisez le `#import` **renommer** attribut pour assigner un alias au symbole dans la bibliothèque de types.