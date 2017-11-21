---
title: "Exécution d’un programme en prétraitement | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6b98d3c03d319c2da397f969f8adf1ec858f72c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="executing-a-program-in-preprocessing"></a>Exécution d'un programme en prétraitement
Pour utiliser le code de sortie d’une commande lors du prétraitement, spécifiez la commande, avec tous les arguments, entre crochets ([]). Les macros sont développées avant l’exécution de la commande. NMAKE remplace la spécification de la commande avec le code de sortie de la commande, qui peut être utilisé dans une expression pour contrôler le prétraitement.  
  
## <a name="see-also"></a>Voir aussi  
 [Expressions utilisées dans le prétraitement d’un makefile](../build/expressions-in-makefile-preprocessing.md)