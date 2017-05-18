---
title: "Indicateurs de contrôle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.flags
dev_langs:
- C++
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9e8d2030edb3c048ec67ddd5a7b0782d2bbfdd9a
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="control-flags"></a>Indicateurs de contrôle
La version Debug de la bibliothèque Runtime C de Microsoft utilise les indicateurs suivants pour contrôler l’allocation de tas et le processus de création de rapports. Pour plus d’informations, consultez [Techniques de débogage CRT](/visualstudio/debugger/crt-debugging-techniques).  
  
|Indicateur|Description|  
|----------|-----------------|  
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Mappe les fonctions du tas de base à leurs équivalents de la version Debug|  
|[_DEBUG](../c-runtime-library/debug.md)|Permet d’utiliser les versions de débogage des fonctions Runtime|  
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Contrôle la façon dont le gestionnaire de tas de débogage effectue le suivi des allocations|  
  
 Ces indicateurs peuvent être définis avec une option de ligne de commande /D ou avec une directive `#define`. Quand l’indicateur est défini avec `#define`, la directive doit apparaître avant l’instruction include du fichier d’en-tête pour les déclarations de routine.  
  
## <a name="see-also"></a>Voir aussi  
 [Variables globales et types standard](../c-runtime-library/global-variables-and-standard-types.md)
