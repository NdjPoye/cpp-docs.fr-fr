---
title: Compilateur avertissement (niveau 4) C4234 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4234
dev_langs: C++
helpviewer_keywords: C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 86a44dfc09e3b0bcb0744115ce4ddfaf8d96f258
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4234"></a>Avertissement du compilateur (niveau 4) C4234
extension non standard utilisée : ' mot_clé ' réservé à un usage ultérieur  
  
 Le compilateur n’implémente pas encore le mot clé que vous avez utilisé.  
  
 Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md). Par exemple, pour que C4234 soit un avertissement de problème de niveau 4  
  
```  
#pragma warning(2:4234)  
```  
  
 dans votre fichier de code source.