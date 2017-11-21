---
title: "Définition des Options de l’éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], LINK
- input files [C++], linker
- linker [C++], ways to set options
- linker [C++], switches
- input files [C++]
- object/library modules
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b64b1dfd342598735124940d01b1bb4939242e10
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setting-linker-options"></a>Définition des options de l'Éditeur de liens
Options de l’éditeur de liens peuvent être définies à l’intérieur ou en dehors de l’environnement de développement. Pour chaque option de l’éditeur de liens explique comment elle peut être définie dans l’environnement de développement. Consultez [les Options de l’éditeur de liens](../../build/reference/linker-options.md) pour une liste complète.  
  
 Lorsque vous exécutez un lien à l’extérieur de l’environnement de développement, vous pouvez spécifier l’entrée dans une ou plusieurs façons :  
  
-   Sur le [ligne de commande](../../build/reference/linker-command-line-syntax.md)  
  
-   À l’aide de [fichiers de commandes](../../build/reference/link-command-files.md)  
  
-   Dans [variables d’environnement](../../build/reference/link-environment-variables.md)  
  
 Options de processus de premier lien spécifié dans la variable d’environnement LINK, suivi d’options dans l’ordre qu’ils sont spécifiés sur la ligne de commande et dans les fichiers de commandes. Si une option est répétée avec différents arguments, le dernier traitée est prioritaire.  
  
 Options s’appliquent à la génération tout entière ; Aucun options ne peuvent être appliquées à des fichiers d’entrée spécifiques.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence à la génération C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)