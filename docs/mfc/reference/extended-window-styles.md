---
title: "Styles de fen&#234;tre &#233;tendus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WS_EX_TOOLWINDOW"
  - "WS_EX_LEFTSCROLLBAR"
  - "WS_EX_RTLREADING"
  - "WS_EX_WINDOWEDGE"
  - "WS_EX_CLIENTEDGE"
  - "WS_EX_STATICEDGE"
  - "WS_EX_LTRREADING"
  - "WS_EX_DLGMODALFRAME"
  - "WS_EX_RIGHTSCROLLBAR"
  - "WS_EX_CONTROLPARENT"
  - "WS_EX_ACCEPTFILES"
  - "WS_EX_TRANSPARENT"
  - "WS_EX_RIGHT"
  - "WS_EX_APPWINDOW"
  - "WS_EX_TOPMOST"
  - "WS_EX_CONTEXTHELP"
  - "WS_EX_MDICHILD"
  - "WS_EX_LEFT"
  - "WS_EX_OVERLAPPEDWINDOW"
  - "WS_EX_PALETTEWINDOW"
  - "WS_EX_NOPARENTNOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "styles de fenêtre étendus"
  - "styles, fenêtres"
  - "WS_EX_ACCEPTFILES (constante)"
  - "WS_EX_APPWINDOW (constante)"
  - "WS_EX_CLIENTEDGE (constante)"
  - "WS_EX_CONTEXTHELP (constante)"
  - "WS_EX_CONTROLPARENT (constante)"
  - "WS_EX_DLGMODALFRAME (constante)"
  - "WS_EX_LEFT (constante)"
  - "WS_EX_LEFTSCROLLBAR (constante)"
  - "WS_EX_LTRREADING (constante)"
  - "WS_EX_MDICHILD (constante)"
  - "WS_EX_NOPARENTNOTIFY (constante)"
  - "WS_EX_OVERLAPPEDWINDOW (constante)"
  - "WS_EX_PALETTEWINDOW (constante)"
  - "WS_EX_RIGHT (constante)"
  - "WS_EX_RIGHTSCROLLBAR (constante)"
  - "WS_EX_RTLREADING (constante)"
  - "WS_EX_STATICEDGE (constante)"
  - "WS_EX_TOOLWINDOW (constante)"
  - "WS_EX_TOPMOST (constante)"
  - "WS_EX_TRANSPARENT (constante)"
  - "WS_EX_WINDOWEDGE (constante)"
ms.assetid: d18e6c69-0a01-49ed-b58a-55b3802b47c1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Styles de fen&#234;tre &#233;tendus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **WS\_EX\_ACCEPTFILES** Spécifie qu'une fenêtre créée avec ce style accepte des fichiers glisser\-déplacer.  
  
-   **WS\_EX\_APPWINDOW** Force une fenêtre de niveau supérieur sur la barre des tâches lorsque la fenêtre est visible.  
  
-   **WS\_EX\_CLIENTEDGE** Spécifie qu'une fenêtre possède une apparence 3D — Autrement dit., une bordure avec un bord enfoncé.  
  
-   **WS\_EX\_CONTEXTHELP** Comprend un point d'interrogation dans la barre de titre de la fenêtre.  Lorsque l'utilisateur clique sur le point d'interrogation, le curseur se transforme en point d'interrogation avec un pointeur.  Si l'utilisateur clique ensuite sur une fenêtre enfant, l'enfant reçoit un message **WM\_HELP**  
  
-   **WS\_EX\_CONTROLPARENT** Permet à l'utilisateur de naviguer parmi les fenêtres enfants de la fenêtre en utilisant la touche TAB.  
  
-   **WS\_EX\_DLGMODALFRAME** Désigne une fenêtre avec une double bordure qui peut \(éventuellement\) être créée avec une barre de titre lorsque vous spécifiez l'indicateur de style **WS\_CAPTION** dans le paramètre `dwStyle`.  
  
-   **WS\_EX\_LAYERED** La fenêtre est une [fenêtre superposée](http://msdn.microsoft.com/library/ms632599\(v=vs.85\).aspx#layered").  Ce style ne peut pas être utilisé si la fenêtre a un [style de classe](http://msdn.microsoft.com/library/ms633574\(v=vs.85\).aspx#class_styles") **CS\_OWNDC** ou **CS\_CLASSDC**.  Toutefois, [!INCLUDE[win8_first](../../mfc/reference/includes/win8_first_md.md)] prend en charge le style **WS\_EX\_LAYERED** pour les fenêtres enfants, où les versions de Windows précédentes le prennent en charge uniquement pour les fenêtres de niveau supérieur.  
  
-   **WS\_EX\_LEFT** Donne à la fenêtre des propriétés génériques d'alignement à gauche.  Il s'agit de la valeur par défaut.  
  
-   **WS\_EX\_LEFTSCROLLBAR** Place une barre de défilement verticale à la gauche de la zone cliente.  
  
-   **WS\_EX\_LTRREADING** Affiche le texte de la fenêtre à l'aide des propriétés d'ordres de lecture de gauche à droite.  Il s'agit de la valeur par défaut.  
  
-   **WS\_EX\_MDICHILD** Crée une fenêtre enfant MDI.  
  
-   **WS\_EX\_NOPARENTNOTIFY** Spécifie qu'une fenêtre enfant créée avec ce style n'envoie pas le message `WM_PARENTNOTIFY` à sa fenêtre parente lorsque la fenêtre enfant est créée ou détruite.  
  
-   **WS\_EX\_OVERLAPPEDWINDOW** Combine les styles **WS\_EX\_CLIENTEDGE** et **WS\_EX\_WINDOWEDGE** .  
  
-   **WS\_EX\_PALETTEWINDOW** Combine les styles **WS\_EX\_WINDOWEDGE** et **WS\_EX\_TOPMOST** .  
  
-   **WS\_EX\_RIGHT** Donne à une fenêtre des propriétés génériques d'alignement à droite.  Cela dépend de la classe de fenêtre.  
  
-   **WS\_EX\_RIGHTSCROLLBAR** Place une barre de défilement verticale \(le cas échéant\) à droite de la zone cliente.  Il s'agit de la valeur par défaut.  
  
-   **WS\_EX\_RTLREADING** Affiche le texte de la fenêtre à l'aide des propriétés d'ordres de lecture de droite à gauche.  
  
-   **WS\_EX\_STATICEDGE** Crée une fenêtre avec un style de bordure tridimensionnel conçu pour être utilisé pour les éléments qui n'acceptent pas d'entrée utilisateur.  
  
-   **WS\_EX\_TOOLWINDOW** Crée une fenêtre Outil, qui est une fenêtre conçue pour être utilisé comme barre d'outils flottante.  Une fenêtre Outil possède une barre de titre plus courte qu'une barre de titre normale, et le titre de la fenêtre est dessiné dans une police de plus petite taille.  Une fenêtre Outil ne s'affiche ni dans la barre des tâches ni dans la fenêtre qui apparaît lorsque l'utilisateur appuie sur ALT\+TAB.  
  
-   **WS\_EX\_TOPMOST** Spécifie qu'une fenêtre créée avec ce style doit être placée au dessus de toutes les fenêtres qui ne sont pas topmost, doit rester au dessus même quand la fenètre est désactivée.  Une application peut utiliser la fonction membre `SetWindowPos` pour ajouter ou supprimer cet attribut.  
  
-   **WS\_EX\_TRANSPARENT** Spécifie qu'une fenêtre créée avec ce style doit être transparente.  Autrement dit, toute fenêtre qui est sous la fenêtre n'est masquée par la fenêtre.  Une fenêtre créée avec ce style reçoit le messages `WM_PAINT` uniquement après que toutes les fenêtres\-sœurs sous elle ont été mises à jour.  
  
-   **WS\_EX\_WINDOWEDGE** Spécifie qu'une fenêtre a une bordure avec un bord relevé.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)