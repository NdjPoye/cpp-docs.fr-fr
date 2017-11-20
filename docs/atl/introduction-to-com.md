---
title: "Introduction à COM | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords: COM
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 236222296b270fe52f43f42a823e3f6f790d08ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="introduction-to-com"></a>Introduction à COM
COM est « modèle d’objet » fondamentales sur les contrôles ActiveX et les OLE sont construits. COM permet à un objet d’exposer ses fonctionnalités à d’autres composants et d’héberger des applications. Il définit comment l’objet expose lui-même et comment cette exposition fonctionne sur les processus et les réseaux. COM définit également le cycle de vie de l’objet.  
  
 Fondamentaux de COM sont ces concepts :  
  
-   [Interfaces](../atl/interfaces-atl.md) — le mécanisme par lequel un objet expose ses fonctionnalités.  
  
-   [IUnknown](../atl/iunknown.md) : l’interface de base sur lequel tous les autres sont basés. Il implémente le décompte de références et l’interface interrogation mécanismes en cours d’exécution via COM.  
  
-   [Décompte](../atl/reference-counting.md) : la méthode par laquelle un objet (ou, plus précisément une interface) décide quand il n’est plus utilisé et n’est donc libérer.  
  
-   [QueryInterface](../atl/queryinterface.md) : la méthode utilisée pour interroger un objet pour une interface donnée.  
  
-   [Marshaling](../atl/marshaling.md) — le mécanisme qui permet aux objets d’être utilisé au-delà des limites du réseau, ce qui permet l’indépendance d’emplacement, de processus et de thread.  
  
-   [Agrégation](../atl/aggregation.md) : une méthode dans laquelle un objet peut faire utiliser d’une autre.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM et ATL](../atl/introduction-to-com-and-atl.md)   
 [Le modèle d’objet composant](http://msdn.microsoft.com/library/windows/desktop/ms694363)

