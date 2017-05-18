---
title: _CRTDBG_MAP_ALLOC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 709ba57e3cca392d2440c7ad528125dc31070cac
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
Quand l’indicateur **_CRTDBG_MAP_ALLOC** est défini dans la version Debug d’une application, la version de base des fonctions du tas est directement mappée à sa version Debug. L’indicateur est utilisé dans Crtdbg.h pour effectuer le mappage. Cet indicateur n’est disponible que quand l’indicateur [_DEBUG](../c-runtime-library/debug.md) a été défini dans l’application.  
  
 Pour plus d’informations sur l’utilisation de la version Debug ou de la version de base d’une fonction de tas, consultez [Utilisation de la version Debug ou de la version de base](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="see-also"></a>Voir aussi  
 [Indicateurs de contrôle](../c-runtime-library/control-flags.md)
