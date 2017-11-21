---
title: 3.3.1 fonction omp_get_wtime | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c5f48f2cbc5cb77d20884632881b779986dac6d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="331-ompgetwtime-function"></a>3.3.1 Fonction omp_get_wtime
Le `omp_get_wtime` fonction retourne une valeur à virgule flottante double précision égale à la durée écoulée totale d’exécution en secondes depuis le « moment donné dans le passé ».  L’heure « réelle dans le passé » est arbitraire, mais il ne peut ne pas changer pendant l’exécution de l’application. Le format est le suivant :  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Il est prévu que la fonction servira pour mesurer le temps écoulé tel qu’indiqué dans l’exemple suivant :  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Les temps retournés sont « délais par thread » par qui est destinée qu’ils ne doivent pas être globalement cohérente sur tous les threads qui participe à une application.