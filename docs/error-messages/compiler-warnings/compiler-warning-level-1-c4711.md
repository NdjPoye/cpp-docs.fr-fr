---
title: Compilateur avertissement (niveau 1) C4711 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4711
dev_langs:
- C++
helpviewer_keywords:
- C4711
ms.assetid: 270506ab-fead-4328-b714-2978113be238
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9be609e0900ad5aea5011fbd880b7952e3e71cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4711"></a>Avertissement du compilateur (niveau 1) C4711
fonction 'fonction' sélectionnée pour expansion inline  
  
 Le compilateur applique la fonctionnalité inline sur la fonction donnée, bien qu’il n’a pas été marqué pour incorporation (inlining).  
  
 C4711 est activé si [/Ob2](../../build/reference/ob-inline-function-expansion.md) est spécifié.  
  
 La fonctionnalité inline est effectuée à la discrétion du compilateur. Cet avertissement possède un caractère informatif.  
  
 Cet avertissement est désactivé par défaut. Pour activer un avertissement, utilisez [#pragma warning](../../preprocessor/warning.md). Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.