---
title: Compilateur avertissement (niveau 3) C4622 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52f4491d26cfa56f48ed479b30daeafe9cc01adf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4622"></a>Avertissement du compilateur (niveau 3) C4622
Remplacement des informations de débogage formées lors de la création de l’en-tête précompilé du fichier objet : 'fichier'  
  
 Les informations CodeView dans le fichier spécifié ont été perdues lorsqu’il a été compilé avec l’option [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (utiliser des en-têtes précompilés).  
  
 Renommez le fichier objet (à l’aide de [/Fo](../../build/reference/fo-object-file-name.md)) lors de la création ou de l’utilisation du fichier d’en-tête précompilé et établissez une liaison avec le nouveau fichier objet.