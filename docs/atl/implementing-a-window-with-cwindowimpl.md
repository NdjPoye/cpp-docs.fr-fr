---
title: "Implementing a Window with CWindowImpl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, fenêtres"
  - "subclassing ATL window classes"
  - "superclassing, ATL"
  - "windows [C++], ATL"
  - "windows [C++], subclassing"
  - "windows [C++], superclassing"
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Window with CWindowImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour implémenter une fenêtre, dérivez une classe d' `CWindowImpl`.  Dans votre classe dérivée, déclarez une table des messages et les fonctions gestionnaires de messages.  Vous pouvez maintenant utiliser votre classe de trois façons :  
  
-   [Créez une fenêtre sur une classe windows](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Surclassement une classe existante windows](#_atl_superclassing_an_existing_windows_class)  
  
-   [Sous\-classe une fenêtre existante](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Créer une fenêtre sur une classe windows  
 `CWindowImpl` contient la macro de [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md) pour déclarer les informations de classe de fenêtre.  Cette macro implémente la fonction d' `GetWndClassInfo` , qui utilise [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) pour définir les informations d'une classe windows.  Lorsque `CWindowImpl::Create` est appelé, cette classe de fenêtre est stockée et une nouvelle fenêtre est créée.  
  
> [!NOTE]
>  `CWindowImpl` passe **NULL** à la macro d' `DECLARE_WND_CLASS` , ce qui signifie qu'ATL génère un nom de classe de fenêtre.  Pour spécifier votre propre nom, passez une chaîne à `DECLARE_WND_CLASS` dans votre `CWindowImpl`classe dérivée.  
  
## Exemple  
 Voici un exemple d'une classe qui implémente une fenêtre sur une classe windows :  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_1.h)]  
  
 Pour créer une fenêtre, créez une instance d' `CMyWindow` puis appelez la méthode de **Créer** .  
  
> [!NOTE]
>  Pour remplacer les informations de classe par défaut de windows, implémentez la méthode d' `GetWndClassInfo` dans votre classe dérivée en définissant les membres d' `CWndClassInfo` aux valeurs appropriées.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> Superclassing une classe existante windows  
 La macro de [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) vous permet de créer une fenêtre que les surclasse les fenêtres existantes classe.  Spécifiez cette macro dans votre `CWindowImpl`classe dérivée.  Comme toute autre fenêtre ATL, les messages sont gérés par une table des messages.  
  
 Lorsque vous utilisez `DECLARE_WND_SUPERCLASS`, une classe windows sera stockée.  Cette classe est la même que la classe existante vous spécifiez, mais remplaceront la procédure de fenêtre par `CWindowImpl::WindowProc` \(ou avec votre fonction qui substituent cette méthode\).  
  
## Exemple  
 Voici un exemple d'une classe qui surclasse la classe standard de modification :  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_2.h)]  
  
 Pour créer la fenêtre acquérir une surclasse de modification, créez une instance d' `CMyEdit` puis appelez la méthode de **Créer** .  
  
##  <a name="_atl_subclassing_an_existing_window"></a> Sous\-classement une fenêtre existante  
 Sous\-classer une fenêtre existante, dérivent une classe d' `CWindowImpl` et déclarez une table des messages, comme dans les deux cas précédents.  Notez, cependant, que vous ne spécifiez aucune information de classe de fenêtre, comme vous sous\-classe une fenêtre existante.  
  
 Au lieu d'appeler **Créer**, appelez `SubclassWindow` et passez le handle vers la fenêtre existante à sous\-classer.  Une fois que la fenêtre est sous\-classée, il utilisera `CWindowImpl::WindowProc` \(ou la fonction qui substituent cette méthode\) pour exécuter des messages dans la table des messages.  Pour détacher une fenêtre sous\-classée de votre objet, appelez `UnsubclassWindow`.  La procédure de fenêtre d'origine de la fenêtre sera alors restaurée.  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)