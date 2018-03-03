---
title: Erreur de ligne de commande D8045 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- D8045
dev_langs:
- C++
helpviewer_keywords:
- D8045
ms.assetid: 01c8808c-bac1-4b4d-8a90-b595f95e9318
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9489535e0a1f9873d2c299ae8a9766bcbb5035dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-line-error-d8045"></a>Erreur de ligne de commande D8045
Impossible de compiler le fichier C 'fichier' avec l’option /clr  
  
 Uniquement les fichiers de code source C++ peuvent être passés à une compilation qui utilise **/CLR**.  Utilisez **/TP** pour compiler un fichier .c en tant que fichier .cpp ; consultez [/Tc, / TP, /TP (spécifier le Type des fichiers Source)](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) pour plus d’informations.  
  
 Pour plus d’informations, consultez l’article [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 L’erreur D8045 peut également se produire si vous compilez une application ATL à l’aide de Visual C++. Consultez [Comment : migrer vers/CLR](../../dotnet/how-to-migrate-to-clr.md) pour plus d’informations.