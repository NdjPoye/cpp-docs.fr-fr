---
title: Affichage des Assertions | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ebfa692f422283e69395639295b3bf2ace1741ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="displaying-assertions"></a>Affichage des Assertions
Si le client connecté à votre service semble cesser de répondre, le service peut avoir déclaré et affiche une boîte de message que vous n’êtes pas en mesure de voir. Vous pouvez le vérifier à l’aide du débogueur de Visual C++ pour déboguer votre code (consultez [Gestionnaire des tâches à l’aide de](../atl/using-task-manager.md) plus haut dans cette section).  
  
 Si vous déterminez que votre service affiche une boîte de message qui n’est pas visible, vous souhaitez peut-être définir la **autoriser le Service à interagir avec le bureau** option avant de réutiliser le service. Cette option est un paramètre de démarrage qui permet à tous les messages affichés par le service sur le bureau. Pour définir cette option, ouvrez l’application Services du panneau, sélectionnez le service, cliquez sur **démarrage**, puis sélectionnez le **autoriser le Service à interagir avec le bureau** option.  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de débogage](../atl/debugging-tips.md)

