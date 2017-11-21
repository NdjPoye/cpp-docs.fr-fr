---
title: "Ajout d’une fonctionnalité au contrôle Composite | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- event handlers [C++], ActiveX controls
- composite controls, handling events
- ActiveX controls [C++], events
ms.assetid: 98f85681-9564-480d-af38-03f9733fe58b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7282ba7eb80fd30175751bb5234818a5e3cf1431
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-functionality-to-the-composite-control"></a>Ajout d’une fonctionnalité au contrôle Composite
Une fois que vous avez inséré les contrôles nécessaires dans le contrôle composite, l’étape suivante implique l’ajout de nouvelles fonctionnalités. Cette nouvelle fonctionnalité se situe généralement en deux catégories :  
  
-   Prise en charge des interfaces supplémentaires et de personnaliser le comportement de votre contrôle composite doté de fonctionnalités supplémentaires spécifiques.  
  
-   Gestion des événements à partir de la relation contenant-contenu contrôle ActiveX (ou contrôles).  
  
 Pour l’objectif et la portée de cet article, le reste de cette section se concentre uniquement sur la gestion des événements à partir de contrôles ActiveX.  
  
> [!NOTE]
>  Si vous avez besoin gérer les messages à partir de contrôles Windows, consultez [implémentation d’une fenêtre](../atl/implementing-a-window.md) pour plus d’informations sur la gestion des messages dans ATL.  
  
 Après avoir inséré un contrôle ActiveX dans la ressource de boîte de dialogue, cliquez sur le contrôle, puis cliquez sur **ajouter un gestionnaire d’événements**. Sélectionnez l’événement que vous souhaitez gérer et cliquez sur **ajouter et modifier des**. Le code de gestionnaire d’événements est ajouté pour le fichier .h du contrôle.  
  
 Points de connexion pour les contrôles ActiveX sur le contrôle composite sont automatiquement connectés et déconnectés via des appels à [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).  
  
## <a name="see-also"></a>Voir aussi  
 [Principes de base des contrôles composites](../atl/atl-composite-control-fundamentals.md)

