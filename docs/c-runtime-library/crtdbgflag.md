---
title: _crtDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f4c3a874d59095d620a04d5ebb6ac88e2bdfa66
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
L'indicateur **_crtDbgFlag** est constitué de cinq champs de bits qui contrôlent la façon dont les allocations de mémoire sur la version Debug du tas sont suivies, vérifiées, signalées et vidées. Les champs de bits de l’indicateur sont définis à l’aide de la fonction [_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md). Cet indicateur et ses champs de bits sont déclarés dans Crtdbg.h. Cet indicateur n’est disponible que quand l’indicateur [_DEBUG](../c-runtime-library/debug.md) a été défini dans l’application.  
  
 Pour plus d’informations sur l’utilisation de cet indicateur avec d’autres fonctions de débogage, consultez [Fonctions de création de rapports sur l’état du tas](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="see-also"></a>Voir aussi  
 [Indicateurs de contrôle](../c-runtime-library/control-flags.md)
