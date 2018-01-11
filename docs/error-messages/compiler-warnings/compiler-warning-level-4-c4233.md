---
title: Compilateur avertissement (niveau 4) C4233 | Documents Microsoft
ms.custom: 
ms.date: 10/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4233
dev_langs: C++
helpviewer_keywords: C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad27d2ec3d59df147d8bfc26372a2d25397e651f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4233"></a>Avertissement du compilateur (niveau 4) C4233

> extension non standard utilisée : '*mot clé*' mot clé uniquement pris en charge en C++, non en C

Le compilateur a compilé votre code source C plutôt que C++, et que vous avez utilisé un mot clé qui n’est pas valide en C++. Le compilateur compile votre fichier source en C si l’extension du fichier source est .c ou si vous utilisez [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md).

Cet avertissement est automatiquement promu en une erreur. Si vous souhaitez modifier ce comportement, utilisez [#pragma warning](../../preprocessor/warning.md). Par exemple, pour que C4233 soit un problème d’avertissement de niveau 4, ajoutez cette ligne à votre fichier de code source :

```cpp
#pragma warning(4:4233)
```
