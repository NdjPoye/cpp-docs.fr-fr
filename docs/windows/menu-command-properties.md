---
title: "Propriétés de commande de menu | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 186790db57c20abf9f67f693ff60029257ebd4f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="menu-command-properties"></a>Propriétés d'une commande de menu
Les informations ci-dessous sont organisées en fonction des propriétés de menu qui s'affichent dans la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window) quand vous sélectionnez une commande de menu. Elles sont répertoriées par ordre alphabétique. Toutefois, la fenêtre Propriétés vous permet également d'afficher ces propriétés par catégorie.  
  
|Propriété|Description|  
|--------------|-----------------|  
|**Break**|Peut avoir l'une des valeurs suivantes :<br /><br /> -   **Aucun** (par défaut) : aucun arrêt.<br />-   **Colonne**: pour les menus statiques, cette valeur permet de placer la commande de menu sur une nouvelle ligne. Pour les menus contextuels, cette valeur permet de placer la commande de menu dans une nouvelle colonne sans ligne de démarcation entre les colonnes. Cette propriété affecte l'apparence du menu uniquement au moment de l'exécution, pas dans l'éditeur de menus.<br />-   **Barre**: identique à Colonne, sauf dans le cas des menus contextuels, où cette valeur sépare la nouvelle colonne de l'ancienne par une ligne verticale. Cette propriété affecte l'apparence du menu uniquement au moment de l'exécution, pas dans l'éditeur de menus.|  
|**Légende**|Texte qui indique la commande de menu (nom du menu). Pour que l'une des lettres de la légende d'une commande de menu devienne une touche mnémonique, faites-la précéder d'une esperluette (&).|  
|**Activé**|Si la valeur est True, la commande de menu est initialement activée. Type : Bool. Valeur par défaut : False.|  
|**Activé**|Si la valeur est **False**, l'élément de menu est désactivé.|  
|**Grisé**|Si la valeur est True, la commande de menu est initialement grisée et inactive. Type : Bool. Valeur par défaut : False.|  
|**Aide**|Aligne l'élément de menu à droite. Par exemple, la commande de menu **? (Aide)** est toujours sur la droite dans toutes les applications Windows. Si vous affectez cette propriété à un élément de menu, celui-ci s'affiche à l'extrémité droite et à la fin du menu. S'applique aux éléments de niveau supérieur. Valeur par défaut : **False**.|  
|**ID**|Symbole défini dans le fichier d'en-tête. Type : symbole, entier ou chaîne entre guillemets. Vous pouvez utiliser n'importe quel symbole couramment disponible dans les éditeurs, même si la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window) ne fournit pas de liste déroulante pour sélectionner des éléments.|  
|**Fenêtre contextuelle**|Si la valeur est True, la commande de menu est un menu contextuel. Type : Bool. Par défaut : True pour les menus de niveau supérieur dans une barre de menus. Sinon, False.|  
|**Invite**|Contient le texte qui s'affiche dans la barre d'état quand cette commande de menu est mise en surbrillance. Le texte est placé dans la table de chaînes avec le même identificateur que la commande de menu. Cette propriété est disponible pour tous les types de projet, mais les fonctionnalités d'exécution sont spécifiques à MFC.|  
|**Justification de droite à gauche**|Aligne à droite la commande de menu dans la barre de menus au moment de l'exécution. Type : Bool. Valeur par défaut : False.|  
|**Ordre de droite à gauche**|Permet d'afficher les commandes de menu de droite à gauche quand l'interface est localisée dans une langue qui se lit de droite à gauche, par exemple l'hébreu ou l'arabe.|  
|**Séparateur**|Si la valeur est True, la commande de menu est un séparateur. Type : Bool. Valeur par défaut : False.|  
  

  
## <a name="requirements"></a>Configuration requise  
 Win32  
  
## <a name="see-also"></a>Voir aussi  
 [Éditeur de menus](../windows/menu-editor.md)