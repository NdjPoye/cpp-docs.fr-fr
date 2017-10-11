---
title: "Erreur irrécupérable C1382 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1382
dev_langs:
- C++
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ddb016e14b01b3bc1dfd45c7d5a8ad1aa489ac3a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1382"></a>Erreur irrécupérable C1382
fichier PCH 'fichier' recompilé depuis la génération de 'obj'. Régénérez cet objet  
  
 Lorsque vous utilisez [LTCG](../../build/reference/ltcg-link-time-code-generation.md), le compilateur a détecté un fichier .pch qui est plus récent qu’un fichier CIL .obj qui pointe vers elle. Les informations contenues dans le fichier CIL .obj sont obsolètes. Reconstruire l’objet.  
  
 C1382 peut également se produire si vous compilez avec **/Yc**, mais également passer plusieurs source des fichiers de code pour le compilateur.  Pour résoudre, n’utilisez pas **/Yc** lors du passage des fichiers de code source multiples au compilateur.  Pour plus d’informations, consultez [/Yc (créer un en-tête précompilé)](../../build/reference/yc-create-precompiled-header-file.md).
