---
title: CCmdUI, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CCmdUI
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efb87fc04ee9ee55806ec4fc1103ded42231b433
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="the-ccmdui-class"></a>CCmdUI, classe
Quand elle achemine une commande de mise à jour vers son gestionnaire, l’infrastructure transmet un pointeur vers le Gestionnaire d’un `CCmdUI` objet (ou un objet d’un `CCmdUI`-classe dérivée). Cet objet représente le bouton de barre d’outils ou élément de menu ou un autre objet d’interface utilisateur qui a généré la commande. Le Gestionnaire de mise à jour appelle les fonctions de membres le `CCmdUI` structure via le pointeur de la mise à jour de l’objet d’interface utilisateur. Voici, par exemple, un gestionnaire de mise à jour pour l’élément de menu Effacer tout :  
  
 [!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]  
  
 Ce gestionnaire appelle la **activer** fonction membre d’un objet avec un accès à l’élément de menu. **Activer** permet d’utiliser l’élément.  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour mettre à jour des objets d’interface utilisateur](../mfc/how-to-update-user-interface-objects.md)

