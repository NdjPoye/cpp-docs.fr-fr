---
title: Où définir des Macros | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e646de4cf67fc249d69fb07789f4c8a3e14bf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="where-to-define-macros"></a>Où définir des macros
Définissez les macros dans une ligne de commande, fichier de commandes, un makefile ou le fichier Tools.ini.  
  
 Dans un makefile ou le fichier Tools.ini, chaque définition de macro doit apparaître sur une ligne distincte et ne peut pas commencer par un espace ou une tabulation. Des espaces ou des onglets autour du signe égal sont ignorés. Tous les [chaîne de caractères](../build/defining-an-nmake-macro.md) sont des littéraux, des espaces et les guillemets de délimitation compris.  
  
 Dans une ligne de commande ou un fichier de commandes, les espaces et tabulations délimitent les arguments et ne peuvent pas entourer le signe égal. Si `string` incorpore des espaces ou des tabulations, mettez la chaîne ou l’intégralité de la macro entre guillemets doubles (« »).  
  
## <a name="see-also"></a>Voir aussi  
 [Définition d’une macro NMAKE](../build/defining-an-nmake-macro.md)