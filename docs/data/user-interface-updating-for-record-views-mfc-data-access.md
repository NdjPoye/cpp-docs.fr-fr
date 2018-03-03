---
title: "Mise à jour de l’Interface utilisateur pour les vues des enregistrements (MFC Data Access) | Documents Microsoft"
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
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68b013f3b1211c42ffc7355df73f47f6520fac1d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Mise à jour de l'interface utilisateur pour les vues des enregistrements (Accès aux données MFC)
`CRecordView`Fournit des gestionnaires de mise à jour de l’interface utilisateur par défaut pour les commandes de navigation. Ces gestionnaires automatisent l'activation et la désactivation des objets d'interface utilisateur (éléments de menu et boutons de barre d'outils). L’Assistant application fournit des menus standard et, si vous choisissez la **barre d’outils ancrable** option, un ensemble de boutons de barre d’outils pour les commandes. Si vous créez une classe de vue d'enregistrement à l'aide de `CRecordView`, vous pouvez ajouter des objets d'interface utilisateur similaires à votre application.  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>Pour créer des ressources de menu avec l'éditeur de menu  
  
1.  Qui fait référence aux informations sur l’utilisation de la [éditeur de menus](../windows/menu-editor.md), créez votre propre menu avec ces quatre commandes.  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Pour créer des boutons de barre d'outils avec l'éditeur de graphismes  
  
1.  Qui fait référence aux informations sur l’utilisation de la [éditeur de barre d’outils](../windows/toolbar-editor.md), modifiez la ressource de barre d’outils pour ajouter des boutons de barre d’outils pour vos commandes de navigation entre les enregistrements.  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la Navigation dans une vue d’enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [À l’aide d’une vue d’enregistrement](../data/using-a-record-view-mfc-data-access.md)