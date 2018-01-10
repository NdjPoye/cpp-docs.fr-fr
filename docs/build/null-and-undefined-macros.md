---
title: "Macros nulles et non définies | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9581b152057655c510f1cbcd4ab29ba8339070b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="null-and-undefined-macros"></a>Macros nulles et non définies
L’expansion des macros nulles et non définies pour les chaînes null, mais une macro définie comme une chaîne null est considérée comme défini dans les expressions de prétraitement. Pour définir une macro comme une chaîne null, spécifiez aucun caractère à l’exception des espaces ou des tabulations après le signe égal (=) dans une ligne de commande ou un fichier de commandes et placez la chaîne null ou la définition des guillemets doubles ( » «). Pour supprimer la définition d’une macro, utilisez **! UNDEF.** Pour plus d’informations, consultez [Directives de prétraitement Makefile](../build/makefile-preprocessing-directives.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Définition d’une macro NMAKE](../build/defining-an-nmake-macro.md)