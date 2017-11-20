---
title: "Qu’est un objet hôte ? (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: host objects
ms.assetid: 4f8da992-b27e-45e8-b5e0-c8b1dcae4fac
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ab37e9a9d3a19f250f52d5f5c60de41968012625
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="what-is-a-host-object"></a>Qu’est un objet hôte ?
Un objet hôte est un objet COM qui représente le conteneur de contrôle ActiveX fourni par ATL pour une fenêtre particulière. L’objet hôte sous-classe la fenêtre conteneur afin qu’elle peut refléter les messages au contrôle, il fournit les interfaces de conteneur nécessaires à utiliser par le contrôle, et expose le [interface IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) et [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) interfaces vous permettent de configurer l’environnement du contrôle.  
  
 Vous pouvez utiliser l’objet hôte pour définir les propriétés ambiantes du conteneur.  
  
## <a name="see-also"></a>Voir aussi  
 [Forum aux questions sur la contenance de contrôles](../atl/atl-control-containment-faq.md)

