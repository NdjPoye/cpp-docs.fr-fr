---
title: "Éviter les problèmes avec les programmes Multithread | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 546f5b5daa88578fc7dd062018257f0929bc0cff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Comment éviter les sources d'incident dans les programmes multithread
Il existe plusieurs problèmes que vous pouvez rencontrer dans la création, la liaison ou l’exécution d’un programme multithread en langage C. Certains des problèmes plus courants sont décrits dans le tableau suivant. (Pour une description similaire à partir du point de vue MFC, consultez [Multithreading : conseils de programmation](../parallel/multithreading-programming-tips.md).)  
  
|Problème|Cause probable|  
|-------------|--------------------|  
|Vous obtenez un message indiquant que votre programme a provoqué une violation de protection.|De nombreuses erreurs de programmation Win32 provoquent des violations de protection. Une cause fréquente de violations de protection est l’affectation indirecte de données à des pointeurs null. Étant donné que cela entraîne de votre programme essaie d’accéder à la mémoire qui n’appartient pas à ce dernier, une violation de la protection est émise.<br /><br /> Un moyen simple de détecter la cause d’une violation de protection consiste à compiler votre programme avec des informations de débogage et exécutez-le via le débogueur dans l’environnement Visual C++. En cas de défaillance de la protection, Windows transfère le contrôle au débogueur, et le curseur est positionné sur la ligne qui a provoqué le problème.|  
|Votre programme génère de nombreuses erreurs de compilation et de liaison.|Vous pouvez éliminer les nombreux problèmes potentiels en définissant le niveau d’avertissement du compilateur à un de ses valeurs les plus élevées et en faisant attention les messages d’avertissement. En utilisant le niveau 3 ou les options au niveau Avertissement de niveau 4, vous pouvez détecter les conversions de données involontaires, les prototypes de fonction manquant et utilisation de fonctions non-ANSI.|  
  
## <a name="see-also"></a>Voir aussi  
 [Multithreading à l’aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)