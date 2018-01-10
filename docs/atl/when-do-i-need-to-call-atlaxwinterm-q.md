---
title: "Quand dois-je appeler AtlAxWinTerm ? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AtlAxWinTerm
dev_langs: C++
helpviewer_keywords: AtlAxWinTerm method
ms.assetid: 0088d494-2d8d-45b4-b582-2af726bd6cbd
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c52c5295108ef01dc23ea9f945850e91a9806d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="when-do-i-need-to-call-atlaxwinterm"></a>Quand dois-je appeler AtlAxWinTerm ?
[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) annule l’inscription de le **« AtlAxWin80 »** classe de fenêtre. Vous devez appeler cette fonction (si vous n’avez plus besoin de créer des fenêtres de l’hôte) une fois que toutes les fenêtres hôtes existantes ont été détruits. Si vous n’appelez pas cette fonction, la classe de fenêtre sera annulée automatiquement lorsque le processus se termine.  
  
## <a name="see-also"></a>Voir aussi  
 Quand dois-je appeler AtlAxWinInit  
[Forum aux questions sur la contenance de contrôles](../atl/atl-control-containment-faq.md)

