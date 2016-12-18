---
title: "Outils d&#233;finis par l&#39;utilisateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "outils définis par l'utilisateur (extensions MFC)"
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Outils d&#233;finis par l&#39;utilisateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC prend en charge les outils définis pour l'utilisateur.  Un outil défini par l'utilisateur est une commande particulière qui exécute un programme externe et spécifié par l'utilisateur.  Vous pouvez utiliser le processus de personnalisation pour gérer les outils définis par l'utilisateur.  Toutefois, vous ne pouvez pas utiliser ce processus si votre objet d'application n'est pas dérivé de [CWinAppEx Class](../mfc/reference/cwinappex-class.md).  Pour plus d'informations sur la personnalisation du code, consultez [Personnalisation pour MFC](../mfc/customization-for-mfc.md).  
  
 Si vous activez la prise en charge des outils définis par l'utilisateur, la boîte de dialogue de personnalisation inclut automatiquement l'onglet **Outils**.  L'illustration suivante présente la page **Outils**.  
  
 ![Onglet Outils de la boîte de dialogue Personnalisation](../mfc/media/custdialogboxtoolstab.png "CustDialogBoxToolsTab")  
Onglet personnalisation de la boîte de dialogue des Outils  
  
## Activer la prise en charge d'outils définis par l'utilisateur  
 Pour activer les outils définis par l'utilisateur dans une application, appelez [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md).  Toutefois, vous devez d'abord définir plusieurs constantes dans les fichiers de ressources de votre application à utiliser comme paramètres pour cet appel.  
  
 Dans l'éditeur de ressources créez une commande factice qui utilise un ID de commande approprié  Dans l'exemple suivant, nous utilisons **ID\_TOOLS\_ENTRY** comme ID de commande  Cet ID de commande signale un emplacement dans un ou plusieurs menus où l'environnement insèrera les outils définis par l'utilisateur.  
  
 Vous devez mettre de côté certains ID consécutifs dans la table de chaînes pour représenter les outils définis par l'utilisateur.  Le nombre de chaînes à mettre de côté est égal au nombre maximal d'outils d'utilisateur que les utilisateurs peuvent définir.  Dans l'exemple suivant, ils sont appelés **ID\_USER\_TOOL1** via **ID\_USER\_TOOL10**.  
  
 Vous pouvez offrir des suggestions aux utilisateurs pour les aider à sélectionner des répertoires et des arguments pour les programmes externes qui seront appelés en tant qu'outils.  Pour cela, créez deux menus contextuels dans l'éditeur de ressources.  Dans l'exemple suivant, ils sont appelés **IDR\_MENU\_ARGS** et **IDR\_MENU\_DIRS**.  Pour chaque commande dans les menus, définissez la chaîne dans la table de chaînes d'application.  L'ID de ressource de la chaîne doit être égal à l'ID de commande  
  
 Vous pouvez également créer une classe dérivée de [CUserTool Class](../mfc/reference/cusertool-class.md) pour remplacer l'implémentation par défaut.  Pour cela, transmettez les informations d'exécution pour votre classe dérivée comme quatrième paramètre dans CWinAppEx::EnableUserTools, au lieu de RUNTIME\_CLASS \([CUserTool Class](../mfc/reference/cusertool-class.md)\).  
  
 Après avoir défini les constantes appropriées, appelez [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) pour activer les outils définis par l'utilisateur.  
  
 L'appel de la méthode suivante montre comment utiliser ces constantes :  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/CPP/user-defined-tools_1.cpp)]  
  
 Dans cet exemple, l'onglet d'outils est inclus dans la boîte de dialogue **Personnalisation**.  L'environnement remplace toute commande qui correspond à l'ID de commande **ID\_TOOLS\_ENTRY** dans n'importe quel élément avec l'ensemble d'outils définis par l'utilisateur lorsqu'un utilisateur ouvre le menu.  Les IDs de commande **ID\_USER\_TOOL1** via **ID\_USER\_TOOL10** sont réservés à l'utilisation des outils définis par l'utilisateur.  La classe [CUserTool Class](../mfc/reference/cusertool-class.md) traite les appels aux outils utilisateur.  L'onglet d'outils de la boîte de dialogue **Personnalisation** fournit des boutons situés à droite de l'argument et des champs d'entrée du répertoire pour accéder aux menus **IDR\_MENU\_ARGS** et **IDR\_MENU\_DIRS**.Lorsqu'un utilisateur sélectionne une commande de l'un de ces menus, l'environnement ajoute à la zone de texte la chaîne qui possède l'ID ressource identique à celui de l'ID de commande.  
  
### Y compris les outils prédéfinis  
 Si vous souhaitez prédéfinir certains outils au démarrage de l'application, vous devez remplacer la méthode [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md) de la fenêtre principale de votre application.  Avec cette méthode, vous devez suivre les étapes suivantes :  
  
##### Pour ajouter de nouveaux outils dans LoadFrame  
  
1.  Obtenir un pointeur vers l'objet [CUserToolsManager Class](../mfc/reference/cusertoolsmanager-class.md) en appelant [CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md).  
  
2.  Pour chaque outil à créer, appelez [CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md).  Cette méthode retourne un pointeur vers un objet [CUserTool Class](../mfc/reference/cusertool-class.md) et ajoute l'outil d'utilisateur créé récemment à la collection interne d'outils.  Si vous avez fourni des informations d'exécution à une classe dérivée de [CUserTool Class](../mfc/reference/cusertool-class.md) comme quatrième paramètre de [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md), [CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md) instanciera et retournera une instance de cette classe à la place.  
  
3.  Pour chaque outil, définissez son étiquette de texte en définissant `CUserTool::m_strLabel` et définissez sa commande en appelant `CUserTool::SetCommand`.  L'implémentation par défaut de [CUserTool Class](../mfc/reference/cusertool-class.md) récupère automatiquement les icônes disponibles du programme spécifié dans l'appel à `SetCommand`.  
  
## Voir aussi  
 [Personnalisation pour MFC](../mfc/customization-for-mfc.md)   
 [CUserTool Class](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager Class](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx Class](../mfc/reference/cwinappex-class.md)