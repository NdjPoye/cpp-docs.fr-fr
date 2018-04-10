---
title: Erreur du compilateur C2692 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: 9253bf70204bfded06189b6688405cabc43bdcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2692"></a>Erreur du compilateur C2692
'nom_fonction' : fonctions entièrement prototypées requises dans le compilateur C avec le ' / clr' option  
  
 Lors de la compilation pour .NET de code managé, le compilateur C requiert des déclarations de fonction ANSI. En outre, si une fonction n’accepte aucun paramètre, il doit déclarer explicitement `void` en tant que le type de paramètre.