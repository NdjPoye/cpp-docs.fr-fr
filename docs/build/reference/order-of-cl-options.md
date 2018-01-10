---
title: Ordre des Options CL | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords: cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef67792b01d4d4dab535bfb180cd70beb2316b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="order-of-cl-options"></a>Ordre des options CL
Options peuvent apparaître n’importe où sur la ligne de commande CL, à l’exception de l’option /link, qui doit avoir lieu en dernier. Le compilateur commence par les options spécifiées dans le [variable d’environnement CL](../../build/reference/cl-environment-variables.md) , puis lit la ligne de commande de gauche à droite, le traitement des fichiers de commandes dans l’ordre où il les trouve. Chaque option s’applique à tous les fichiers sur la ligne de commande. Si CL rencontre des options en conflit, elle utilise l’option la plus à droite.  
  
## <a name="see-also"></a>Voir aussi  
 [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)