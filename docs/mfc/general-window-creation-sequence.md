---
title: "Séquence de création de fenêtre générale | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59bed4387a6b8e6edeb504e29d221e76a0b39d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="general-window-creation-sequence"></a>Séquence de création d'une fenêtre générale
Lorsque vous créez une fenêtre de la fenêtre de votre choix, comme un enfant, l’infrastructure utilise beaucoup le même processus que celui décrit dans [création de Document/vue](../mfc/document-view-creation.md).  
  
 Toutes les classes de fenêtre fournis par l’emploi MFC [construction en deux étapes](../mfc/one-stage-and-two-stage-construction-of-objects.md). Autrement dit, lors d’un appel de C++ **nouveau** (opérateur), le constructeur alloue et initialise un objet C++ mais ne crée pas de fenêtre Windows correspondante. Qui est effectué par la suite en appelant le [créer](../mfc/reference/cwnd-class.md#create) fonction membre de l’objet de fenêtre.  
  
 Le **créer** fonction membre crée la fenêtre Windows et stocke son `HWND` dans le membre de données publiques de l’objet C++ [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd). **Créer** donne davantage de flexibilité sur les paramètres de création. Avant d’appeler **créer**, vous pouvez souhaiter enregistrer une classe de fenêtre avec la fonction globale [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) afin de définir les styles d’icône et de la classe pour le frame.  
  
 Pour les fenêtres frames, vous pouvez utiliser la [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) fonction membre au lieu de **créer**. `LoadFrame`crée la fenêtre de Windows à l’aide de moins de paramètres. Il obtient le nombre de valeurs par défaut à partir des ressources, y compris la légende du frame, icône, table d’accélérateurs et menu.  
  
> [!NOTE]
>  Icône, table d’accélérateurs, les ressources de menu doivent avoir un ID de ressource commun, tel que **IDR_MAINFRAME**, pour pouvoir être chargé par LoadFrame.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Que voulez-vous en savoir plus  
  
-   [Objets fenêtres](../mfc/window-objects.md)  
  
-   [Inscrire des classes de fenêtre « »](../mfc/registering-window-classes.md)  
  
-   [Destruction d’objets fenêtres](../mfc/destroying-window-objects.md)  
  
-   [Création de fenêtres frame de document](../mfc/creating-document-frame-windows.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Création de fenêtres](../mfc/creating-windows.md)

