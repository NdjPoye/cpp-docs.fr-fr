---
title: "Évaluateur d’expression, erreur CXX0033 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0033
dev_langs: C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 618dbe464adc64f36e35b9c329eb476166b8b5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>Évaluateur d'expression, erreur CXX0033
erreur dans les informations de type OMF  
  
 Le fichier exécutable n’avait pas un format de module valide d’objet (OMF) pour le débogage.  
  
 Cette erreur est identique à CAN0033.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Le fichier exécutable n’a pas été créé avec l’éditeur de liens fourni avec cette version de Visual C++. Reconstruire le code de l’objet à l’aide de la version actuelle de LINK.exe.  
  
2.  Le fichier .exe a peut-être été endommagé. Recompilez et rééditez le programme.