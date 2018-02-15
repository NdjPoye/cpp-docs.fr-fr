---
title: "Quand l'automation à distance convient-elle ? | Microsoft Docs"
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
- Remote Automation, DCOM
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ad6eef0bbaad7860e7f4310ce283efe18c668eb
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="where-does-remote-automation-fit-in"></a>Quand l'automation à distance convient-elle ?
DCOM a été publiée en 1996 et est disponible avec les plateformes 32 bits et 64 bits uniquement. L’équipe Visual Basic chez Microsoft a constaté toujours de Visual Basic utilise Automation pour permettre à ses composants de communiquer. L’absence d’une version distribuée limitait l’utilisation de ces fonctionnalités dans les environnements d’entreprise, l’équipe de développement Visual Basic 4.0 Édition entreprise décidé étudier la création de son propre ensemble de composants de la communication à distance pour l’automatisation parties de OLE et COM. Clairement, le but principal était pour garantir que le résultat serait compatible avec et peut être remplacé par DCOM lorsqu’il est devenu disponible. Ils puis a été effectué pour implémenter l’Automation à distance (RA) pour les plateformes Windows 16 bits et 32 bits.  
  
 Automation à distance n’est pas liée à un langage spécifique, mais jusqu'à ce que la version de Visual C++ 4.2 Édition entreprise, il a été expédiée uniquement avec Visual Basic 4.0. N’oubliez pas que l’Automation à distance est entièrement dépendante de DCOM. Si vous avez la possibilité d’utiliser DCOM au lieu de l’Automation à distance dans vos applications, vous devez le faire. Toutefois, il existe des scénarios où l’Automation à distance est plus appropriée :  
  
-   Partout où vous avez des clients 16 bits.  
  
-   Si votre organisation n’a pas encore restauré une version compatible DCOM de Windows NT ou Windows 95.  
  
-   Si vous mettez à niveau une suite de l’application existante qui utilise l’Automation à distance pour utiliser des composants C++ à la place d’un ou plusieurs composants de Visual Basic.  
  
 Aucune différence entre les programmes créés pour utiliser l’Automation à distance et ceux créés pour utiliser Automation via DCOM n’est nécessaire, et les utilitaires de configuration rendent très simple basculer entre l’Automation à distance et DCOM. Par conséquent, il n’est pas difficile à mettre à niveau une application à partir de l’Automation à distance DCOM une fois l’infrastructure en place.  
  
## <a name="see-also"></a>Voir aussi  
 [Que fournit l’Automation à distance](what-does-remote-automation-provide-q.md)   
 [Historique de DCOM](../mfc/history-of-dcom.md)
