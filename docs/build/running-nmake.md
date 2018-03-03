---
title: "Exécution de NMAKE | Documents Microsoft"
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
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6c39612cf4df47665f7ea3d529b77ee4e70ce8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="running-nmake"></a>Exécution de NMAKE
## <a name="syntax"></a>Syntaxe  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>Notes  
 Builds NMAKE uniquement spécifiés *cibles* ou, si aucun n’est spécifié, la première cible dans le fichier Make. La première cible du makefile peut être une [pseudocible](../build/pseudotargets.md) qui génère d’autres cibles. NMAKE utilise les makefiles spécifié avec l’option /F ; Si /F n’est pas spécifié, il utilise le fichier Makefile dans le répertoire actif. Si aucun makefile n’est spécifié, il utilise des règles d’inférence pour générer de ligne de commande *cibles*.  
  
 Le `commandfile` fichier texte (ou fichier réponse) contient une entrée de ligne de commande. D’autres entrées peuvent précéder ou suivre`commandfile`. Un chemin d’accès est autorisé. Dans `commandfile`, sauts de ligne sont considérés comme des espaces. Placez les définitions de macros entre guillemets si elles contiennent des espaces.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Options de NMAKE](../build/nmake-options.md)  
  
 [Tools.ini et NMake](../build/tools-ini-and-nmake.md)  
  
 [Codes de sortie de NMAKE](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>Voir aussi  
 [NMAKE, référence](../build/nmake-reference.md)