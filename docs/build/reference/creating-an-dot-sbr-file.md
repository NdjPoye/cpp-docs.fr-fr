---
title: "Création d’une. Les fichiers sbr | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d87b71daaf5d7b37e67c2c0e56e844bd5251a490
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-sbr-file"></a>Création d'un fichier .sbr
Les fichiers d’entrée pour BSCMAKE sont des fichiers .sbr. Le compilateur crée un fichier .sbr pour chaque fichier objet (.obj) il compile. Lorsque vous générez ou mettre à jour votre fichier d’informations de consultation, tous les fichiers .sbr pour votre projet doivent être disponibles sur le disque.  
  
 Pour créer un fichier .sbr contenant toutes les informations possibles, spécifiez [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md).  
  
 Pour créer un fichier .sbr qui ne contient pas de symboles locales, spécifiez [/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md). Si les fichiers .sbr contiennent des symboles locaux, vous pouvez néanmoins les omettre dans le fichier .bsc à l’aide de BSCMAKE [option /El](../../build/reference/bscmake-options.md)`.`  
  
 Vous pouvez créer un fichier .sbr sans effectuer une compilation complète. Par exemple, vous pouvez spécifier l’option /Zs au compilateur d’effectuer une vérification de la syntaxe et de générer un fichier .sbr si vous spécifiez /FR ou /Fr.  
  
 Le processus de génération peut être plus efficace si les fichiers .sbr sont compressés au préalable pour supprimer les définitions non référencées. Le compilateur compresse automatiquement les fichiers .sbr.  
  
## <a name="see-also"></a>Voir aussi  
 [Génération d’un fichier .bsc](../../build/reference/building-a-dot-bsc-file.md)