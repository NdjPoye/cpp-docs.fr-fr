---
title: "Macros récursives | Documents Microsoft"
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
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e8d9ef7f194151fb3259712759d0c29ed157d564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="recursion-macros"></a>Macros récursives
Utiliser des macros de récursivité pour appeler NMAKE de manière récursive. Les sessions récursives héritent des macros de ligne de commande et la variable d’environnement et des informations concernant Tools.ini. Ils n’héritent pas des règles d’inférence définies makefile ou **. SUFFIXES** et **. PRÉCIEUX** spécifications. Pour passer des macros à une session NMAKE récursive, définir une variable d’environnement avec jeu avant l’appel récursif, définissez une macro dans la commande pour l’appel récursif ou définissez une macro dans Tools.ini.  
  
|Macro|Définition|  
|-----------|----------------|  
|**RENDRE**|Commande utilisée initialement pour appeler NMAKE.<br /><br /> La macro $ (Make) donne le chemin d’accès complet à nmake.exe.|  
|**MAKEDIR**|Répertoire actif où NMAKE a été appelé.|  
|**MAKEFLAGS**|Options actuellement en vigueur. Utiliser comme `/$(MAKEFLAGS)`.  Notez que /F n’est pas inclus.|  
  
## <a name="see-also"></a>Voir aussi  
 [Macros spéciales de NMAKE](../build/special-nmake-macros.md)