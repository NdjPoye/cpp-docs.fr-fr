---
title: "Temps écoulé : Les Classes à usage général | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- dates, calculating intervals
- elapsed time, calculating
- elapsed time
- time, elapsed
- intervals, date and time
- calculations, date and time
ms.assetid: e5c5d3d2-ce1d-409e-875c-98848434e716
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51eea60669fb7ad35525d65013ffc8420649349b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="elapsed-time-general-purpose-classes"></a>Temps écoulé : Les Classes à usage général
La procédure suivante montre comment calculer la différence entre deux `CTime` objets et obtenir un `CTimeSpan` résultat.  
  
#### <a name="to-calculate-elapsed-time"></a>Pour calculer le temps écoulé  
  
1.  Utilisez le `CTime` et `CTimeSpan` objets pour calculer le temps écoulé, comme suit :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#174](../atl-mfc-shared/codesnippet/cpp/elapsed-time-general-purpose-classes_1.cpp)]  
  
     Une fois que vous avez calculée `elapsedTime`, vous pouvez utiliser les fonctions membres de `CTimeSpan` pour extraire les composants de la valeur de temps écoulé.  
  
## <a name="see-also"></a>Voir aussi  
 [Date et heure : classes à usage général](../atl-mfc-shared/date-and-time-general-purpose-classes.md)

