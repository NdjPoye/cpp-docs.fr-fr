---
title: Compilateur avertissement (niveau 4) C4234 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4234
dev_langs:
- C++
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68f4b2c3b51caf5e0438c2ead293823885b73157
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4234"></a>Avertissement du compilateur (niveau 4) C4234
extension non standard utilisée : ' mot_clé ' réservé à un usage ultérieur  
  
 Le compilateur n’implémente pas encore le mot clé que vous avez utilisé.  
  
 Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md). Par exemple, pour que C4234 soit un avertissement de problème de niveau 4  
  
```  
#pragma warning(2:4234)  
```  
  
 dans votre fichier de code source.