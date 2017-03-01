---
title: Styles de zone de liste | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- LBS_NOSEL constant
- LBS_NOREDRAW constant
- LBS_HASSTRINGS constant
- LBS_OWNERDRAWFIXED constant
- LBS_WANTKEYBOARDINPUT constant
- LBS_STANDARD constant
- LBS_MULTIPLESEL constant
- LBS_OWNERDRAWVARIABLE constant
- LBS_DISABLENOSCROLL constant
- LBS_NODATA constant
- list boxes, styles
- LBS_EXTENDEDSEL constant
- LBS_MULTICOLUMN constant
- LBS_NOTIFY constant
- LBS_USETABSTOPS constant
- LBS_NOINTEGRALHEIGHT constant
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8e038e5cef50bd15df85c9d7f8b213b54ed03825
ms.lasthandoff: 02/24/2017

---
# <a name="list-box-styles"></a>Styles de zone de liste
-   **LBS_DISABLENOSCROLL** la zone de liste affiche une désactivé verticale barre de défilement lorsque la zone de liste ne contient pas suffisamment d’éléments pour faire défiler. Sans ce style, la barre de défilement est masquée lorsque la zone de liste ne contient pas assez d'éléments.  
  
-   **LBS_EXTENDEDSEL** l’utilisateur peut sélectionner plusieurs éléments à l’aide de la touche MAJ et la souris ou les combinaisons de touches spéciales.  
  
-   **LBS_HASSTRINGS** spécifie une zone de liste owner-draw qui contient des éléments composés de chaînes. La zone de liste contient la mémoire et les pointeurs des chaînes afin que l'application puisse utiliser la fonction membre `GetText` pour récupérer le texte d'un élément particulier.  
  
-   **LBS_MULTICOLUMN** spécifie une zone de liste multicolonne défilement horizontal. La fonction membre `SetColumnWidth` définit la largeur des colonnes.  
  
-   **LBS_MULTIPLESEL** sélection de chaînes est modifiée chaque fois que l’utilisateur clique ou double-clique sur la chaîne. Plusieurs chaînes peuvent être sélectionnées.  
  
-   **LBS_NODATA** spécifie une zone de liste sans données. Spécifiez ce style lorsque le nombre d'éléments dans la zone de liste dépasse&1000;. Une zone de liste sans données doit également disposer du **LBS_OWNERDRAWFIXED** de style, mais ne doit pas avoir la **LBS_SORT** ou **LBS_HASSTRINGS** style.  
  
     Une zone de liste sans données s'apparente à une zone de liste personnalisée par son propriétaire sauf qu'elle ne contient aucune chaîne ou donnée bitmap d'un élément. Les commandes d'ajout, d'insertion ou de suppression d'un élément ignorent toutes les données d'un élément donné ; les requêtes de recherche d'une chaîne dans la zone de liste échouent toujours. Le système envoie le message `WM_DRAWITEM` dans la fenêtre propriétaire lorsqu'un élément doit être dessiné. Le membre itemID de la structure `DRAWITEMSTRUCT` passée avec le message `WM_DRAWITEM` spécifie le numéro de ligne de l'élément à tracer. Une zone de liste sans données n'envoie pas de message `WM_DELETEITEM`.  
  
-   **LBS_NOINTEGRALHEIGHT** la taille de la zone de liste est exactement la taille spécifiée par l’application lors de la création de la zone de liste. Généralement, Windows redimensionne une zone de liste pour qu'elle n'affiche aucun élément de manière partielle.  
  
-   **LBS_NOREDRAW** affichage de la zone de liste n’est pas mis à jour lorsque des modifications sont apportées. Ce style peut être modifié à tout moment en envoyant un **WM_SETREDRAW** message.  
  
-   **LBS_NOSEL** Spécifie que la zone de liste contient des éléments qui peuvent être consultés mais non sélectionnés.  
  
-   **LBS_NOTIFY** fenêtre parente reçoit un message d’entrée chaque fois que l’utilisateur clique ou double-clique sur une chaîne.  
  
-   **LBS_OWNERDRAWFIXED** le propriétaire de la zone de liste est responsable du dessin de son contenu ; les éléments dans la zone de liste sont la même hauteur.  
  
-   **LBS_OWNERDRAWVARIABLE** le propriétaire de la zone de liste est responsable du dessin de son contenu ; les éléments dans la zone de liste sont variables en hauteur.  
  
-   **LBS_SORT** chaînes dans la zone de liste sont triés par ordre alphabétique.  
  
-   **LBS_STANDARD** chaînes dans la zone de liste sont triés par ordre alphabétique, et la fenêtre parente reçoit un message d’entrée chaque fois que l’utilisateur clique ou double-clique sur une chaîne. La zone de liste contient des bordures de chaque côté.  
  
-   **LBS_USETABSTOPS** permet à une zone de liste de reconnaître et développer des caractères de tabulation en dessinant ses chaînes. Les positions des onglets par défaut correspondent à 32 unités de boîte de dialogue. (L'unité de boîte de dialogue est une distance horizontale ou verticale. Une unité de boîte de dialogue horizontale est égale à un quart de l'unité de largeur de base de dialogue actuelle. Les unités de dialogue sont calculées en fonction de la hauteur et de la largeur de la police système actuelle. Le **GetDialogBaseUnits** fonction Windows retourne des unités de la boîte de dialogue actuelle en pixels.) Ce style ne doit pas être utilisé avec **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** le propriétaire de la zone de liste reçoit `WM_VKEYTOITEM` ou `WM_CHARTOITEM` des messages chaque fois que l’utilisateur appuie sur une touche alors que la zone de liste a le focus. Cela permet à une application d'effectuer un traitement spécial sur l'entrée de clavier.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Styles de zone de liste](http://msdn.microsoft.com/library/windows/desktop/bb775149)


