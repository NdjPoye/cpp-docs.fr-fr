---
title: "Puis-je héberger plusieurs contrôles dans une fenêtre unique ? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [ATL], hosting multiple
- windows [C++], hosting multiple controls
ms.assetid: 3a967a1a-7e7e-42e3-8eed-f7bde912363f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5fa1a1b914d7d9725e8f2d9858f0481bb7aa24a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Puis-je héberger plusieurs contrôles dans une fenêtre unique ?
Il n’est pas possible d’héberger plusieurs contrôles dans une seule fenêtre d’hôte ATL. Chaque fenêtre de l’hôte est conçu pour contenir exactement un contrôle à la fois (ainsi, un mécanisme simple pour la gestion des propriétés ambiantes message réflexion et par contrôle). Toutefois, si vous avez besoin de l’utilisateur de voir plusieurs contrôles dans une fenêtre unique, il est très simple pour créer plusieurs fenêtres de l’ordinateur hôte en tant qu’enfants de cette fenêtre.  
  
## <a name="see-also"></a>Voir aussi  
 [Forum aux questions sur la contenance de contrôles](../atl/atl-control-containment-faq.md)

