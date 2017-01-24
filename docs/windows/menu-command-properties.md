---
title: "Menu Command Properties | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menu items, properties"
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Menu Command Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les informations ci\-dessous sont organisées en fonction des propriétés de menu qui s'affichent dans la [fenêtre Propriétés](../Topic/Properties%20Window.md) quand vous sélectionnez une commande de menu. Elles sont répertoriées par ordre alphabétique. Toutefois, la fenêtre Propriétés vous permet également d'afficher ces propriétés par catégorie.  
  
|Propriété|Description|  
|---------------|-----------------|  
|**Break**|Peut avoir l'une des valeurs suivantes :<br /><br /> -   **Aucun** \(par défaut\) : aucun arrêt.<br />-   **Colonne** : pour les menus statiques, cette valeur permet de placer la commande de menu sur une nouvelle ligne. Pour les menus contextuels, cette valeur permet de placer la commande de menu dans une nouvelle colonne sans ligne de démarcation entre les colonnes. Cette propriété affecte l'apparence du menu uniquement au moment de l'exécution, pas dans l'éditeur de menus.<br />-   **Barre** : identique à Colonne, sauf dans le cas des menus contextuels, où cette valeur sépare la nouvelle colonne de l'ancienne par une ligne verticale. Cette propriété affecte l'apparence du menu uniquement au moment de l'exécution, pas dans l'éditeur de menus.|  
|**Légende**|Texte qui indique la commande de menu \(nom du menu\). Pour que l'une des lettres de la légende d'une commande de menu devienne une touche mnémonique, faites\-la précéder d'une esperluette \(&\).|  
|**Activé**|Si la valeur est True, la commande de menu est initialement activée. Type : Bool. Valeur par défaut : False.|  
|**Activé**|Si la valeur est **False**, l'élément de menu est désactivé.|  
|**Grisé**|Si la valeur est True, la commande de menu est initialement grisée et inactive. Type : Bool. Valeur par défaut : False.|  
|**Aide**|Aligne l'élément de menu à droite. Par exemple, la commande de menu **? \(Aide\)** est toujours sur la droite dans toutes les applications Windows. Si vous affectez cette propriété à un élément de menu, celui\-ci s'affiche à l'extrémité droite et à la fin du menu. S'applique aux éléments de niveau supérieur. Valeur par défaut : **False**.|  
|**ID**|Symbole défini dans le fichier d'en\-tête. Type : symbole, entier ou chaîne entre guillemets. Vous pouvez utiliser n'importe quel symbole couramment disponible dans les éditeurs, même si la [fenêtre Propriétés](../Topic/Properties%20Window.md) ne fournit pas de liste déroulante pour sélectionner des éléments.|  
|**Fenêtre contextuelle**|Si la valeur est True, la commande de menu est un menu contextuel. Type : Bool. Par défaut : True pour les menus de niveau supérieur dans une barre de menus. Sinon, False.|  
|**Invite**|Contient le texte qui s'affiche dans la barre d'état quand cette commande de menu est mise en surbrillance. Le texte est placé dans la table de chaînes avec le même identificateur que la commande de menu. Cette propriété est disponible pour tous les types de projet, mais les fonctionnalités d'exécution sont spécifiques à MFC.|  
|**Justification de droite à gauche**|Aligne à droite la commande de menu dans la barre de menus au moment de l'exécution. Type : Bool. Valeur par défaut : False.|  
|**Ordre de droite à gauche**|Permet d'afficher les commandes de menu de droite à gauche quand l'interface est localisée dans une langue qui se lit de droite à gauche, par exemple l'hébreu ou l'arabe.|  
|**Séparateur**|Si la valeur est True, la commande de menu est un séparateur. Type : Bool. Valeur par défaut : False.|  
  
 Pour plus d'informations sur l'ajout de ressources aux projets managés, consultez [Ressources dans les applications](../Topic/Resources%20in%20Desktop%20Apps.md) dans le *Guide du développeur .NET Framework.* Pour plus d’informations sur l’ajout manuel de fichiers de ressources aux projets managés, l’accès aux ressources, l’affichage de ressources statiques et l’assignation de chaînes de ressources à des propriétés, consultez [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [Menu Editor](../mfc/menu-editor.md)