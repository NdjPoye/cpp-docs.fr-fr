---
title: Tools.ini et NMAKE | Documents Microsoft
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
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4516c3206a08c2b9ee32aea4bbb669ce4cdf0d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini et NMAKE
NMAKE lit Tools.ini avant de lire les makefiles, sauf si /R est utilisée. Il recherche Tools.ini tout d’abord dans le répertoire actif, puis dans le répertoire spécifié par la variable d’environnement INIT. La section des paramètres NMAKE dans le fichier d’initialisation commence par `[NMAKE]` et peut contenir toutes les informations d’un makefile. Spécifiez un commentaire sur une ligne séparée commençant par un signe dièse (#).  
  
## <a name="see-also"></a>Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)