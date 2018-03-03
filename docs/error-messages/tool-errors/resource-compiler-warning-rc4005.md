---
title: Avertissement RC4005 du compilateur de ressources | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f27de973f0ff18493c182bdf1feb3f2812f39af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4005"></a>Avertissement RC4005 du compilateur de ressources 
'identificateur' : redéfinition de macro  
  
 L’identificateur est défini à deux reprises. Le compilateur a utilisé la deuxième définition de macro.  
  
 Cet avertissement peut être provoqué par une macro est définie sur la ligne de commande et dans le code avec un `#define` la directive. Elle peut également être due par des macros importées à partir des fichiers include.  
  
 Pour éliminer l’avertissement, supprimez une des définitions ou utilisez un `#undef` directive avant la seconde définition.