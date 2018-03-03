---
title: Dispositifs de suivi | Documents Microsoft
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
- trackers [MFC]
- OLE applications [MFC], trackers
- applications [OLE], trackers
- tracking OLE items [MFC]
- OLE containers [MFC], trackers
- CDC class [MFC], trackers
- CRectTracker class [MFC], implementing trackers
- OLE server applications [MFC], trackers
ms.assetid: dcd09399-6637-4621-80e5-d12670429787
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29e4d3c556a5f7b6b3aed5daa0285ea6c2c15447
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="trackers"></a>Dispositifs de suivi
Le [CRectTracker](../mfc/reference/crecttracker-class.md) classe fournit une interface utilisateur entre des éléments rectangulaires dans votre application et votre utilisateur en fournissant un ensemble de styles d’affichage. Ces styles comprennent des bordures continues, hachurées ou en pointillés ; un motif hachuré qui recouvre l’élément ; et les poignées de redimensionnement qui peuvent se trouve à l’extérieur ou à l’intérieur d’une bordure. Dispositifs de suivi sont souvent utilisés conjointement avec les éléments OLE, c'est-à-dire, les objets dérivés de `COleClientItem`. Les rectangles du dispositif de suivi donnent des indications sur l’état actuel de l’élément.  
  
 L’exemple OLE MFC [OCLIENT](../visual-cpp-samples.md) montre une interface commune à l’aide de dispositifs de suivi et des éléments du client OLE à partir du point de vue d’une application conteneur. Pour une démonstration des différents styles et les capacités d’un objet de mise hors tension, consultez l’exemple général MFC [mise hors tension](../visual-cpp-samples.md).  
  
 Pour plus d’informations sur l’implémentation de dispositifs de suivi dans votre application OLE, consultez [dispositifs de suivi : implémentation de dispositifs de suivi dans votre Application OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)  
  
## <a name="see-also"></a>Voir aussi  
 [OLE](../mfc/ole-in-mfc.md)   
 [COleClientItem, classe](../mfc/reference/coleclientitem-class.md)
