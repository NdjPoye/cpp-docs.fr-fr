---
title: Pseudocibles | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 761b71f05840c86516563df79d45cc1bb018fbba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pseudotargets"></a>Pseudocibles
Une pseudocible est une étiquette utilisée à la place d’un nom de fichier dans une ligne de dépendance. Il est interprété comme un fichier qui n’existe pas et par conséquent, est obsolète. NMAKE suppose que les horodatage d’une pseudocible sont la plus récente de tous ses dépendants. Si elle ne dispose d’aucune dépendance, l’heure actuelle est supposé. Si une pseudocible est utilisée en tant que cible, ses commandes sont toujours exécutées. Une pseudocible utilisée comme dépendant doit également apparaître en tant que cible dans une autre dépendance. Toutefois, cette dépendance n’a pas besoin d’avoir un bloc de commandes.  
  
 Noms des pseudocibles obéissent règles de syntaxe pour les cibles. Toutefois, si le nom ne possède pas d’extension (autrement dit, s’il ne contient pas une période), il peut dépasser la limite de 8 caractères pour les noms de fichiers et peut comporter jusqu'à 256 caractères.  
  
## <a name="see-also"></a>Voir aussi  
 [Targets (Cibles MSBuild)](../build/targets.md)