---
title: "Contr&#244;les ActiveX MFC&#160;: sous-classement d&#39;un contr&#244;le Windows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "precreatewindow"
  - "IsSubclassed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoSuperclassPaint (méthode)"
  - "IsSubclassed (méthode)"
  - "contrôles ActiveX MFC, créer"
  - "contrôles ActiveX MFC, contrôles sous-classés"
  - "OnDraw (méthode), contrôles ActiveX MFC"
  - "PreCreateWindow (méthode), substituer"
  - "messages réfléchis, dans les contrôles ActiveX"
  - "sous-classer"
  - "sous-classer des contrôles Windows"
  - "sous-classer, contrôles Windows"
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Contr&#244;les ActiveX MFC&#160;: sous-classement d&#39;un contr&#244;le Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le processus de sous\-classement d'un contrôle Windows commun pour créer un contrôle ActiveX.  Le sous\-classement d'un contrôle Windows existant est un moyen rapide de développer un contrôle ActiveX.  Le nouveau contrôle a les fonctionnalités du contrôle Windows sous\-classé, telles que la peinture et la réponse aux clics de souris.  L'exemple de [BUTTON](../top/visual-cpp-samples.md) des contrôles ActiveX MFC est un exemple de sous\-classement d'un contrôle Windows.  
  
 Pour sous\-classer un contrôle Windows, complétez les tâches suivantes :  
  
-   [Remplacez les méthodes IsSubclassedControl et PreCreateWindow de COleControl](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [Modifiez la méthode OnDraw](#_core_modifying_the_ondraw_member_function)  
  
-   [Traitez tous les messages du contrôle ActiveX \(OCM\) renvoyés au contrôle](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  La majeure partie de ce travail est réalisée pour vous par l'Assistant Contrôle ActiveX si vous sélectionnez le contrôle pour être sous\-classé à l'aide de la liste déroulante **Select Parent Window Class** dans la page **Paramètres du contrôle**.  
  
 Consultez l'article Q243454 de la Base de connaissances pour plus d'informations sur le sous\-classement d'un contrôle.  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> Remplacer IsSubclassedControl et PreCreateWindow  
 Pour remplacer `PreCreateWindow` et `IsSubclassedControl`, ajoutez les lignes suivantes du code à la section `protected` de la déclaration de classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxSub#1](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_1.h)]  
  
 Dans le fichier d'implémentation du contrôle \(.CPP\), ajoutez les lignes de code suivantes pour implémenter les fonctions remplacées :  
  
 [!code-cpp[NVC_MFC_AxSub#2](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_2.cpp)]  
  
 Notez que, dans cet exemple, le contrôle bouton Windows est spécifié dans `PreCreateWindow`.  Toutefois, tous les contrôles Windows standard peuvent être sous\-classés.  Pour plus d'informations sur les contrôles Windows standard, consultez l'[Contrôles](../mfc/controls-mfc.md).  
  
 Lors du sous\-classement d'un contrôle Windows, vous pouvez préciser le style de fenêtre \(**WS\_**\) ou le style de fenêtre étendue \(**WS\_EX\_**\) à utiliser lors de la création de la fenêtre du contrôle.  Vous pouvez définir des valeurs pour les paramètres de la méthode `PreCreateWindow` en modifiant les champs de structure **cs.style** et  **cs.dwExStyle**.  Les modifications apportées à ces champs doivent être effectuées à l'aide d'une opération `OR`, pour conserver les indicateurs de valeur par défaut définis par la classe `COleControl`.  Par exemple, si le contrôle sous\-classe le contrôle bouton et que vous voulez un contrôle qui apparaisse comme une case à cocher, insérez la ligne de code suivante dans l'implémentation de `CSampleCtrl::PreCreateWindow`, avant l'instruction RETURN :  
  
 [!code-cpp[NVC_MFC_AxSub#3](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_3.cpp)]  
  
 Cette opération ajoute l'indicateur de **BS\_CHECKBOX**, en laissant l'indicateur de style par défaut \(**WS\_CHILD**\) de la classe `COleControl` intact.  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a> Modifier la méthode OnDraw  
 Si vous souhaitez que votre contrôle sous\-classé conserve la même apparence que le contrôle Windows correspondant, la méthode `OnDraw` pour le contrôle doit contenir un seul appel à la méthode `DoSuperclassPaint`, comme dans l'exemple suivant :  
  
 [!code-cpp[NVC_MFC_AxSub#4](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_4.cpp)]  
  
 La méthode `DoSuperclassPaint`, implémentée par `COleControl`, utilise la procédure d'affichage du contrôle Windows pour dessiner le contrôle dans le contexte matériel spécifié, dans le rectangle englobant.  Cela rend le contrôle visible même s'il n'est pas actif.  
  
> [!NOTE]
>  La méthode `DoSuperclassPaint` fonctionne uniquement avec ces types de contrôles qui fournissent un contexte de périphérique à être passé comme **wParam** d'un message `WM_PAINT`.  Cela inclut certains contrôles Windows standard, tels que **SCROLLBAR** et **BUTTON**, et tous les contrôles communs.  Pour les contrôles qui ne prennent pas en charge ce comportement, vous devez fournir votre propre code pour afficher correctement un contrôle inactif.  
  
##  <a name="_core_handling_reflected_window_messages"></a> Gérer les messages reflétés de la fenêtre  
 Les contrôles Windows envoient généralement certains messages de fenêtre vers la fenêtre parente.  Certains de ces messages, comme **WM\_COMMAND**, notifient d'une action par l'utilisateur.  D'autres, telles que `WM_CTLCOLOR`, sont utilisés pour obtenir les informations de la fenêtre parente.  Un contrôle ActiveX communique généralement avec la fenêtre parente par d'autres moyens.  Les notifications sont communiquées en expédiant des événements \(envoi de notifications d'événements\), ainsi que des informations sur le conteneur de contrôle sont obtenues lors de l'accès aux propriétés ambiantes du conteneur.  Comme ces techniques de communication existent, les conteneurs de contrôle ActiveX ne sont pas sensés traiter les messages de fenêtre envoyés par le contrôle.  
  
 Pour empêcher le conteneur de recevoir les messages de fenêtre envoyés par un contrôle Windows sous\-classé, `COleControl` crée une fenêtre supplémentaire pour servir de parent du contrôle.  Cette fenêtre supplémentaire, appelée un « réflecteur », n'est créée que pour un contrôle ActiveX qui sous\-classe un contrôle Windows et a la même taille et la position que la fenêtre de contrôle.  La fenêtre réflecteur intercepte certains messages de fenêtre et les envoie au contrôle.  Le contrôle, dans la procédure d'affichage, peut ensuite traiter ces messages réfléchis en utilisant les actions appropriées pour un contrôle ActiveX \(par exemple, déclencher un événement\).  Voir [ID des message de fenêtre réfléchis](../mfc/reflected-window-message-ids.md) pour obtenir la liste des messages de fenêtre interceptés et leurs messages réfléchis correspondants.  
  
 Un conteneur de contrôles ActiveX peut être conçu pour exécuter le renvoi de message lui\-même,  éliminant le besoin de`COleControl` de créer la fenêtre de réflection et de réduire la charge d'exécution pour un contrôle Windows sous\-classé.  `COleControl` détecte si le conteneur prend en charge cette fonctionnalité en cherchant une propriété ambiante de MessageReflect avec une valeur de **TRUE**.  
  
 Pour traiter un message de fenêtre réfléchi, ajoutez une entrée à la carte de message de contrôle et implémentez une fonction gestionnaire.  Comme les messages réfléchis ne font pas partie de l'ensemble standard de messages définis par Windows, l'Affichage de classes ne prend pas en charge l'ajout de ces gestionnaires de messages.  Toutefois, il n'est pas difficile d'ajouter un gestionnaire manuellement.  
  
 Pour ajouter un gestionnaire de messages pour un message de fenêtre réfléchi manuellement, procédez comme suit :  
  
-   Dans le fichier .H de la classe de contrôle, déclarez une fonction gestionnaire.  La fonction doit être d'un type de retour **LRESULT** et avoir deux paramètres, de types **WPARAM** et **LPARAM** respectivement.  Par exemple :  
  
     [!code-cpp[NVC_MFC_AxSub#5](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_5.h)]  
    [!code-cpp[NVC_MFC_AxSub#6](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_6.h)]  
  
-   Dans le fichier .cpp de la classede contrôle , ajoutez une entrée `ON_MESSAGE` à la table des messages.  Les paramètres de cette entrée doivent être l'identificateur de message et le nom de la fonction gestionnaire.  Par exemple :  
  
     [!code-cpp[NVC_MFC_AxSub#7](../mfc/codesnippet/CPP/mfc-activex-controls-subclassing-a-windows-control_7.cpp)]  
  
-   Également dans le fichier .cpp, implémentez la méthode **OnOcmCommand** pour traiter le message réfléchi.  Les paramètres de **wParam** et de **lParam** sont identiques à ceux du message d'origine de la fenêtre.  
  
 Pour obtenir un exemple de la façon dont les messages réfléchis sont traités, reportez\-vous à l'exemple de [BUTTON](../top/visual-cpp-samples.md) des contrôles ActiveX MFC.  Il montre un gestionnaire **OnOcmCommand** qui détecte le code de notification **BN\_CLICKED** et répond en déclenchant \(émettant\) un événement Click.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)