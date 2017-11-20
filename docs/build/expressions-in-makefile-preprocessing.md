---
title: "Expressions de prétraitement d’un Makefile | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 32de1d1eb3262e1fca0a00048a61d3129347cb19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expressions-in-makefile-preprocessing"></a>Expressions utilisées dans le prétraitement d'un makefile
Le **! IF** ou **! Si** `constantexpression` se compose de constantes entières (notation décimale ou en langage C), les constantes de chaîne ou de commandes. Utilisez des parenthèses pour regrouper les expressions. Les expressions utiliser C-style entier long signé arithmétiques ; nombres se présentent sous forme de 32 bits de complément à 2 comprise entre - 2147483648 et 2147483647.  
  
 Expressions peuvent utiliser des opérateurs qui agissent sur des valeurs constantes, les codes de sortie des commandes, chaînes, macros et chemins d’accès de système de fichiers.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Sur quels éléments souhaitez-vous obtenir des informations supplémentaires ?  
 [Opérateurs de prétraitement d’un makefile](../build/makefile-preprocessing-operators.md)  
  
 [Exécution d’un programme en prétraitement](../build/executing-a-program-in-preprocessing.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Prétraitement d’un makefile](../build/makefile-preprocessing.md)