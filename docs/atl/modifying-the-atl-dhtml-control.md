---
title: "Modifying the ATL DHTML Control | Microsoft Docs"
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
  - "DHTML controls"
  - "DHTML controls, modifier"
  - "contrôles HTML, modifier"
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modifying the ATL DHTML Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Assistant Contrôle ATL fournit le code de démarrage afin de pouvoir générer et exécuter le contrôle, et vous pouvez voir comment les méthodes sont écrites dans les fichiers projet et comment les appels DHTML dans le code C\+\+ du contrôle à l'aide de les méthodes d'expédition.  Vous pouvez ajouter toute méthode d'expédition à l'interface.  Ensuite, vous pouvez appeler les méthodes dans la ressource HTML.  
  
#### Pour modifier le contrôle ATL DHTML  
  
1.  Dans l'Affichage de classes, développez le projet de contrôle.  
  
     Notez que l'interface qui se termine par « interface » a une méthode, `OnClick`.  L'interface qui ne se termine pas par « interface » n'a aucune méthode.  
  
2.  Ajoutez une méthode appelée `MethodInvoked`à l'interface qui ne se termine pas par « interface ».  
  
     Cette méthode sera ajoutée à l'interface utilisée dans le conteneur de contrôle de l'interaction de conteneur, pas à l'interface utilisée par dynamic HTML pour interagir avec le contrôle.  Seul le conteneur peut appeler cette méthode.  
  
3.  Recherchez la méthode déracinée\- dans le fichier.cpp et ajoutez le code pour afficher un message, par exemple :  
  
     [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  Ajoutez une autre méthode appelée `HelloHTML`, seule cette fois, l'ajoutez à l'interface qui se termine par « interface ». Recherchez la méthode déracinée\- d' `HelloHTML` dans le fichier.cpp et ajoutez le code pour afficher un message, par exemple :  
  
     [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  Ajoutez une troisième méthode, `GoToURL`, à l'interface qui ne se termine pas par « interface ». Implémentent cette méthode en appelant [IWebBrowser2::Navigate](https://msdn.microsoft.com/en-us/library/aa752133.aspx), comme suit :  
  
     [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/CPP/modifying-the-atl-dhtml-control_3.cpp)]  
  
     Vous pouvez utiliser les méthodes d' **IWebBrowser2** parce qu'ATL fournit un pointeur vers cette interface pour vous dans le fichier .h.  
  
 Ensuite, modifiez la ressource HTML pour appeler les méthodes créées.  Vous ajouterez trois boutons pour appeler ces méthodes.  
  
#### Pour modifier la ressource HTML  
  
1.  Dans l'explorateur de solutions, double\-cliquez sur le fichier .htm pour afficher la ressource HTML.  
  
     Examinez le HTML, notamment les appels aux méthodes externes d'expédition windows.  Le HTML appelle la méthode d' `OnClick` du projet, et les paramètres indiquent le corps du contrôle \(`theBody`\) et de la couleur pour assigner \("`red`"\).  Le texte suivant l'appel de méthode est l'étiquette qui apparaît sur le bouton.  
  
2.  Ajoutez une autre méthode d' `OnClick` , seule modifier la couleur.  Par exemple :  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
    ```  
  
     Cette méthode crée un bouton, intitulé **Refresh**, que l'utilisateur peut cliquer pour retourner le contrôle à l'origine, arrière\-plan blanc.  
  
3.  Ajoutez l'appel à la méthode d' `HelloHTML` que vous avez créée.  Par exemple :  
  
    ```  
    <br>  
    <br>  
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
    ```  
  
     Cette méthode crée un bouton, intitulé **HelloHTML**, que l'utilisateur peut cliquer pour afficher le message d' `HelloHTML` .  
  
 Vous pouvez maintenant générer et [testez le contrôle modifié DHTML](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## Voir aussi  
 [Prise en charge pour un contrôle DHTML](../atl/atl-support-for-dhtml-controls.md)