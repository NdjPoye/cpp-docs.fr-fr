---
title: Styles de zone de liste | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f52734e26d1965811aded67bc1e1dde6a2c28bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="list-box-styles"></a>Styles de zone de liste
-   **LBS_DISABLENOSCROLL** la zone de liste affiche une désactivé verticale barre de défilement lorsque la zone de liste ne contient pas assez d’éléments à faire défiler. Sans ce style, la barre de défilement est masquée lorsque la zone de liste ne contient pas assez d'éléments.  
  
-   **LBS_EXTENDEDSEL** l’utilisateur peut sélectionner plusieurs éléments à l’aide de la touche MAJ et la souris ou les combinaisons de touches spéciales.  
  
-   **LBS_HASSTRINGS** spécifie une zone de liste owner-draw qui contient des éléments composés de chaînes. La zone de liste contient la mémoire et les pointeurs des chaînes afin que l'application puisse utiliser la fonction membre `GetText` pour récupérer le texte d'un élément particulier.  
  
-   **LBS_MULTICOLUMN** spécifie une zone de liste multicolonne avec défilement horizontal. La fonction membre `SetColumnWidth` définit la largeur des colonnes.  
  
-   **LBS_MULTIPLESEL** sélection de chaînes est modifiée chaque fois que l’utilisateur clique ou double-clique sur la chaîne. Plusieurs chaînes peuvent être sélectionnées.  
  
-   **LBS_NODATA** spécifie une zone de liste sans données. Spécifiez ce style lorsque le nombre d'éléments dans la zone de liste dépasse 1000. Une zone de liste sans données doit également avoir le **LBS_OWNERDRAWFIXED** de style, mais ne doit pas avoir la **LBS_SORT** ou **LBS_HASSTRINGS** style.  
  
     Une zone de liste sans données s'apparente à une zone de liste personnalisée par son propriétaire sauf qu'elle ne contient aucune chaîne ou donnée bitmap d'un élément. Les commandes d'ajout, d'insertion ou de suppression d'un élément ignorent toutes les données d'un élément donné ; les requêtes de recherche d'une chaîne dans la zone de liste échouent toujours. Le système envoie le message `WM_DRAWITEM` dans la fenêtre propriétaire lorsqu'un élément doit être dessiné. Le membre itemID de la structure `DRAWITEMSTRUCT` passée avec le message `WM_DRAWITEM` spécifie le numéro de ligne de l'élément à tracer. Une zone de liste sans données n'envoie pas de message `WM_DELETEITEM`.  
  
-   **LBS_NOINTEGRALHEIGHT** la taille de la zone de liste correspond exactement à la taille spécifiée par l’application lors de la création de la zone de liste. Généralement, Windows redimensionne une zone de liste pour qu'elle n'affiche aucun élément de manière partielle.  
  
-   **LBS_NOREDRAW** affichage de la zone de liste n’est pas mis à jour lorsque des modifications sont apportées. Ce style peut être modifié à tout moment en envoyant un **WM_SETREDRAW** message.  
  
-   **LBS_NOSEL** Spécifie que la zone de liste contient des éléments qui peuvent être affichés, mais pas sélectionnées.  
  
-   **LBS_NOTIFY** fenêtre parente reçoit un message d’entrée à chaque fois que l’utilisateur clique ou double-clique sur une chaîne.  
  
-   **LBS_OWNERDRAWFIXED** le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments dans la zone de liste ont la même hauteur.  
  
-   **LBS_OWNERDRAWVARIABLE** le propriétaire de la zone de liste est chargé de dessiner son contenu ; les éléments dans la zone de liste sont en hauteur.  
  
-   **LBS_SORT** chaînes dans la zone de liste sont triés par ordre alphabétique.  
  
-   **LBS_STANDARD** chaînes dans la zone de liste sont triés par ordre alphabétique, et la fenêtre parente reçoit un message d’entrée à chaque fois que l’utilisateur clique ou double-clique sur une chaîne. La zone de liste contient des bordures de chaque côté.  
  
-   **LBS_USETABSTOPS** permet à une zone de liste de reconnaître et de développer des caractères de tabulation lors du dessin de ses chaînes. Les positions des onglets par défaut correspondent à 32 unités de boîte de dialogue. (L'unité de boîte de dialogue est une distance horizontale ou verticale. Une unité de boîte de dialogue horizontale est égale à un quart de l'unité de largeur de base de dialogue actuelle. Les unités de dialogue sont calculées en fonction de la hauteur et de la largeur de la police système actuelle. Le **GetDialogBaseUnits** fonction Windows retourne, unités de base, la boîte de dialogue active en pixels.) Ce style ne doit pas être utilisé avec **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** le propriétaire de la zone de liste reçoit `WM_VKEYTOITEM` ou `WM_CHARTOITEM` messages chaque fois que l’utilisateur appuie sur une touche alors que la zone de liste a le focus d’entrée. Cela permet à une application d'effectuer un traitement spécial sur l'entrée de clavier.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Styles de zone de liste](http://msdn.microsoft.com/library/windows/desktop/bb775149)

