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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f50dff4acd216521c8ad67e13f42ecca4f783e37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
Quand l’indicateur **_CRTDBG_MAP_ALLOC** est défini dans la version Debug d’une application, la version de base des fonctions du tas est directement mappée à sa version Debug. L’indicateur est utilisé dans Crtdbg.h pour effectuer le mappage. Cet indicateur n’est disponible que quand l’indicateur [_DEBUG](../c-runtime-library/debug.md) a été défini dans l’application.  
  
 Pour plus d’informations sur l’utilisation de la version Debug ou de la version de base d’une fonction de tas, consultez [Utilisation de la version Debug ou de la version de base](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="see-also"></a>Voir aussi  
 [Indicateurs de contrôle](../c-runtime-library/control-flags.md)