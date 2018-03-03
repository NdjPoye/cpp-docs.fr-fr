---
title: "Utilisation de CToolTipCtrl pour créer et manipuler un objet CToolTipCtrl | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CToolTipCtrl
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da4c98e327d2d78050410e75869c894d73324281
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>Utilisation de CToolTipCtrl pour créer et manipuler un objet CToolTipCtrl
Voici un exemple de [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) utilisation :  
  
### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Pour créer et manipuler un objet CToolTipCtrl  
  
1.  Construire la `CToolTipCtrl` objet.  
  
2.  Appelez [créer](../mfc/reference/ctooltipctrl-class.md#create) pour créer le contrôle commun Windows info-bulle et l’attacher à la `CToolTipCtrl` objet.  
  
3.  Appelez [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) pour inscrire un outil avec le contrôle info-bulle, afin que les informations stockées dans l’info-bulle s’affiche lorsque le curseur se trouve sur l’outil.  
  
4.  Appelez [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) pour définir les informations qui tient à jour une info-bulle pour un outil.  
  
5.  Appelez [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) pour définir un nouveau rectangle englobant pour un outil.  
  
6.  Appelez [HitTest](../mfc/reference/ctooltipctrl-class.md#hittest) pour tester un point pour déterminer s’il s’agit du rectangle englobant de l’outil donné et, si tel est le cas, récupérer des informations sur l’outil.  
  
7.  Appelez [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) pour récupérer un nombre des outils inscrit avec le contrôle info-bulle.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)

