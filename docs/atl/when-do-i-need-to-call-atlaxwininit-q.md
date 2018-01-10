---
title: "Quand dois-je appeler AtlAxWinInit ? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinInit
dev_langs: C++
helpviewer_keywords: AtlAxWinInit method
ms.assetid: 080b9cfe-d85a-4439-a9e9-ab3966ebaa8e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 69dfcfbe0c8c05d275a5f3a8f86c30b0e59bd3a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwininit"></a>Quand dois-je appeler AtlAxWinInit ?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) enregistre la **« AtlAxWin80 »** classe de fenêtre (plus quelques messages de fenêtre personnalisés) afin que cette fonction doit être appelée avant d’essayer de créer une fenêtre hôte. Toutefois, vous n’ont toujours besoin d’appeler cette fonction explicitement, depuis l’hébergement API (et les classes qui les utilisent) appellent souvent cette fonction pour vous. Il n’existe aucun risque d’appeler cette fonction plusieurs fois. .  
  
## <a name="see-also"></a>Voir aussi  
 Quand dois-je appeler AtlAxWinTerm     
 [Forum aux questions sur la contenance de contrôles](../atl/atl-control-containment-faq.md)
