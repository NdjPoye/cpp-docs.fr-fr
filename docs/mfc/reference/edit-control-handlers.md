---
title: "Gestionnaires de contrôle d’édition | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_EN_ERRSPACE
- ON_EN_UPDATE
- ON_EN_VSCROLL
- ON_EN_HSCROLL
- ON_EN_KILLFOCUS
- ON_EN_MAXTEXT
- ON_EN_SETFOCUS
- ON_EN_CHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_EN_ERRSPACE macro [MFC]
- ON_EN_SETFOCUS macro [MFC]
- ON_EN_UPDATE macro [MFC]
- ON_EN_MAXTEXT macro [MFC]
- ON_EN_CHANGE macro [MFC]
- ON_EN_HSCROLL macro [MFC]
- ON_EN_VSCROLL macro [MFC]
- ON_EN_KILLFOCUS macro [MFC]
- edit controls [MFC], edit control handlers
ms.assetid: 55b88b5e-12b5-4422-b03e-c8c2f27d095c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 7599a7ca1c486de453fb3404fa69cab8a09e2d0d
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="edit-control-handlers"></a>Gestionnaires de contrôles d'édition
Les entrées de mappage suivantes correspondent au prototype de fonction.  
  
|Entrée de mappage|Prototype de fonction|  
|---------------|------------------------|  
|ON_EN_CHANGE ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_ERRSPACE ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_HSCROLL ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_KILLFOCUS ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_MAXTEXT ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_SETFOCUS ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_UPDATE ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
|ON_EN_VSCROLL ( \<id >, \<memberFxn >)|afx_msg, void memberFxn () ;|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)


