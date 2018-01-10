---
title: "Comment : afficher des informations de commande dans la barre d’état | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da836f48592d97b3526c568eb9d9a830428f53a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Comment : afficher les informations sur les commandes dans la barre d'état
Lorsque vous exécutez l’Assistant Application pour créer le squelette de votre application, vous pouvez prendre en charge une barre d’outils et une barre d’état. Qu’une seule option dans l’Assistant Application prend en charge les deux. Lorsqu’une barre d’état est présente, l’application fournit automatiquement des commentaires utiles lorsque l’utilisateur déplace le pointeur sur les éléments dans les menus. L’application affiche automatiquement une chaîne d’invite dans la barre d’état lorsque l’élément de menu est mise en surbrillance. Par exemple, lorsque l’utilisateur déplace le pointeur sur le **couper** commande sur le **modifier** menu, la barre d’état peut afficher « Coupe la sélection et le place dans le Presse-papiers » dans la zone de message de la barre d’état. L’invite aide l’utilisateur à comprendre l’objectif de l’élément de menu. Cela fonctionne également lorsque l’utilisateur clique sur un bouton de barre d’outils.  
  
 Vous pouvez ajouter à l’aide de cette barre d’état en définissant des chaînes d’invite pour les éléments de menu que vous ajoutez au programme. Pour ce faire, fournissez les chaînes d’invite lorsque vous modifiez les propriétés de l’élément de menu dans l’éditeur de menus. Les chaînes que vous définissez sont stockées dans le fichier de ressources de l’application ; ils ont les mêmes ID que les commandes qu’elles expliquent.  
  
 Par défaut, l’Assistant Application ajoute `AFX_IDS_IDLEMESSAGE`, l’ID d’un message « Prêt » standard, qui s’affiche lorsque le programme attend de nouveaux messages. Si vous spécifiez l’option aide contextuelle dans l’Assistant Application, le message est modifié pour « De l’aide, appuyez sur F1. »  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)

