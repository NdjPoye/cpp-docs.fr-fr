---
title: "Tester les erreurs d’extraction | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232dbd4312bbb8a0f16b6095622680f070ff2905
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="testing-for-extraction-errors"></a>Tester les erreurs d'extraction
Les fonctions de traitement des erreurs de sortie, présentées dans [Fonctions de traitement des erreurs](../standard-library/output-file-stream-member-functions.md), s’appliquent aux flux d’entrée. Il est important de tester les erreurs lors de l’extraction. Examinez cette instruction :  
  
```  
cin>> n;  
```  
  
 Si `n` est un entier signé, une valeur supérieure à 32 767 (la valeur maximale autorisée ou MAX_INT) définit le bit `fail` du flux et l’objet `cin` devient inutilisable. Toutes les extractions ultérieures entraînent un retour immédiat sans valeur stockée.  
  
## <a name="see-also"></a>Voir aussi  
 [Flux d’entrée](../standard-library/input-streams.md)

