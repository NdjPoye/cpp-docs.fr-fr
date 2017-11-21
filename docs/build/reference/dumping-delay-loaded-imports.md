---
title: "Dump des importations à chargement différé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2104165bf466473d89270eb502e3357713579f38
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="dumping-delay-loaded-imports"></a>Dump des importations à chargement différé
Importations à chargement différé peuvent être extraites à l’aide de [dumpbin /imports](../../build/reference/imports-dumpbin.md) et présentent des informations légèrement différentes importations standard. Ils sont isolés dans leur propre section de vidage /imports et sont étiquetés explicitement en tant qu’importations à chargement différé. S’il existe de décharger les informations présentes dans l’image, qui est indiquée. Si des informations de liaison présents, le cachet de date/heure de la DLL cible est indiqué, ainsi que les adresses liées des importations.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de l’éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)