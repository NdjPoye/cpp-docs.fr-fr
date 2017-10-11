---
title: Erreur du compilateur C2692 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6e65c0310dfd82f86b49193fb173bb483fbd4333
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2692"></a>Erreur du compilateur C2692
'nom_fonction' : fonctions entièrement prototypées requises dans le compilateur C avec le ' / clr' option  
  
 Lors de la compilation pour .NET de code managé, le compilateur C requiert des déclarations de fonction ANSI. En outre, si une fonction n’accepte aucun paramètre, il doit déclarer explicitement `void` en tant que le type de paramètre.
