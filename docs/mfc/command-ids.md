---
title: ID de commande | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b651c734fbd7098705801aefcaa490293a4d661d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="command-ids"></a>ID de commande
Une commande est entièrement décrite par son identificateur de commande seul (codé dans le **WM_COMMAND** message). Cet ID est attribué à l’objet d’interface utilisateur qui génère la commande. En règle générale, les ID sont nommés pour la fonctionnalité de l’objet d’interface utilisateur à qu'ils sont attribués.  
  
 Par exemple, un élément Effacer tout dans le menu Edition peut avoir un ID comme **ID_EDIT_CLEAR_ALL**. La bibliothèque de classes prédéfinit certains identificateurs, notamment pour les commandes que le framework gère elle-même, tel que **ID_EDIT_CLEAR_ALL** ou `ID_FILE_OPEN`. Vous allez créer vous-même autres ID de commande.  
  
 Lorsque vous créez vos propres menus dans Visual C++ de l’éditeur de menu, il est conseillé de suivre la bibliothèque de classes de convention de dénomination comme illustré par `ID_FILE_OPEN`. [Commandes standard](../mfc/standard-commands.md) explique les commandes standard définis par la bibliothèque de classes.  
  
## <a name="see-also"></a>Voir aussi  
 [Objets d’interface utilisateur et ID de commande](../mfc/user-interface-objects-and-command-ids.md)

