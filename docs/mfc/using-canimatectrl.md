---
title: Utilisation de CAnimateCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CAnimateCtrl
dev_langs: C++
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f27fd24c3c4334476c78ba0b59c90cbbb0d51f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-canimatectrl"></a>Utilisation de CAnimateCtrl
Un contrôle animation, représenté par la classe [CAnimateCtrl](../mfc/reference/canimatectrl-class.md), est une fenêtre qui affiche une image au format de la vidéo entrelacée AVI (Audio), le format audio/vidéo Windows standard. Un clip AVI est une série d’images bitmap, comme un film.  
  
 Étant donné que votre thread continue de s’exécuter pendant que le clip AVI s’affiche, une utilisation courante d’un contrôle animation consiste à indiquer l’activité du système pendant une longue opération. Par exemple, la boîte de dialogue Rechercher de Windows affiche une loupe qui se déplace en tant que le système recherche un fichier.  
  
 Contrôles animation peuvent lire uniquement des clips AVI simples et ils ne prennent pas en charge son. (Pour obtenir une liste complète des limitations, consultez [CAnimateCtrl](../mfc/reference/canimatectrl-class.md).) Étant donné que les fonctionnalités d’un contrôle animation sont très limitées et sujets à modification, vous devez utiliser une alternative tels que le contrôle MCIWnd si vous avez besoin d’un contrôle pour fournir des fonctions d’enregistrement et/ou de lecture multimédia. Pour plus d’informations sur le contrôle MCIWnd, consultez la documentation multimédia.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Utilisation d’un contrôle Animation](../mfc/using-an-animation-control.md)  
  
-   [Notifications envoyées par les contrôles d’animation](../mfc/notifications-sent-by-animation-controls.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)

