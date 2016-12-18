---
title: "Menus et ressource&#160;: fusion de menus | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "coordonner la disposition des menus"
  - "menus (C++), documents OLE (applications)"
  - "fusionner la barre d'outils et la barre d'état"
  - "conteneurs OLE, menus et ressources"
  - "barres d'état, documents OLE (applications)"
  - "barres d'outils (C++), documents OLE (applications)"
  - "édition visuelle, menus et ressources d'applications"
ms.assetid: 80b6bb17-d830-4122-83f0-651fc112d4d1
caps.latest.revision: 9
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Menus et ressource&#160;: fusion de menus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les étapes nécessaires pour que les applications OLE de document gèrent la modification visuelle et l'activation sur place correctement.  L'activation sur place constitue un défi pour les applications conteneur et serveur \(composant\).  L'utilisateur reste dans la même fenêtre cadre \(dans le contexte du document conteneur\) mais exécute en réalité une autre application \(serveur\).  Cela requiert la coordination entre les ressources du conteneur et les applications serveur.  
  
 Les rubriques traitées dans cet article sont les suivantes :  
  
-   [Dispositions de menu](#_core_menu_layouts)  
  
-   [barres d'outils et barres d'état ;](#_core_toolbars_and_status_bars)  
  
##  <a name="_core_menu_layouts"></a> Dispositions de menu  
 La première étape consiste à coordonner les dispositions de menu.  Pour plus d'informations, consultez la section **Création de Menu** dans [Considérations relatives à la programmation de menu](https://msdn.microsoft.com/en-us/library/ms647557.aspx) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Les applications conteneur doivent créer un nouveau menu à utiliser uniquement lorsque des éléments imbriqués sont activés sur place.  Au minimum, ce menu doit inclure les éléments suivants, dans l'ordre indiqué :  
  
1.  Menu Fichier identique à celui utilisé quand des fichiers sont ouverts. \(Généralement aucun autre élément de menu n'est placé avant l'élément suivant.\)  
  
2.  Deux séparateurs consécutifs.  
  
3.  Menu Fenêtre identique à celui utilisé lorsque des fichiers sont ouverts \(uniquement si l'application conteneur dans une application MDI\).  Certaines applications peuvent avoir d'autres menus, par exemple le menu d'options, qui appartiennent à ce groupe, qui reste dans le menu lorsqu'un élément incorporé est activé sur place.  
  
    > [!NOTE]
    >  Il peut y avoir d'autres menus qui affectent la vue du document conteneur, tel que le zoom.  Ces menus de conteneur apparaissent entre les deux séparateurs dans cette ressource menu.  
  
 Les applications de serveur \(composant\) doivent également créer un nouveau menu spécifiquement pour l'activation sur place.  Elle doit correspondre au menu utilisé lorsque des fichiers sont ouverts, mais sans les éléments de menu, tels que le fichier et la fenêtre qui manipulent le document serveur au lieu des données.  En général, ce menu comprend les opérations suivantes :  
  
1.  Menu d'Edition identique à celui utilisé quand des fichiers sont ouverts.  
  
2.  Separateur.  
  
3.  Menus de modification d'objet, tels que le menu stylet dans l'exemple d'application de dessin à main levée.  
  
4.  Separateur.  
  
5.  Menu Aide  
  
 Pour obtenir un exemple, regardez la disposition des menus témoin sur place pour un conteneur et un serveur.  Les détails de chaque élément de menu ont été supprimés pour rendre l'exemple plus clair.  Le menu sur place d'un conteneur comporte les entrées suivantes :  
  
```  
IDR_CONTAINERTYPE_CNTR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&File C1"  
    MENUITEM SEPARATOR  
    POPUP "&Zoom C2"  
    MENUITEM SEPARATOR  
    POPUP "&Options C3"  
    POPUP "&Window C3"  
END  
```  
  
 Les séparateurs consécutifs indiquent où la première partie du menu du serveur doit accéder.  Maintenant regardez dans le menu sur place du serveur :  
  
```  
IDR_SERVERTYPE_SRVR_IP MENU PRELOAD DISCARDABLE   
BEGIN  
    POPUP "&Edit S1"  
    MENUITEM SEPARATOR  
    POPUP "&Format S2"  
    MENUITEM SEPARATOR  
    POPUP "&Help S3"  
END  
```  
  
 Les séparateurs ici montrent où le second groupe d'éléments de menu du conteneur doit accéder.  La structure de menu résultante lorsqu'un objet de ce serveur est activé sur place dans ce conteneur ressemble à ceci :  
  
```  
BEGIN  
    POPUP "&File C1"  
    POPUP "&Edit S1"  
    POPUP "&Zoom C2"  
    POPUP "&Format S2"  
    POPUP "&Options C3  
    POPUP "&Window C3"  
    POPUP "&Help S3"  
END  
```  
  
 Comme vous pouvez le voir, les séparateurs ont été remplacés par les différents groupes du menu de chaque application.  
  
 Les tables d'accélérateurs associées au menu sur place doivent aussi être prises en compte par l'application serveur.  Le conteneur les incorporera à ses tables d'accélérateurs.  
  
 Lorsqu'un élément incorporé est activé sur place, le framework charge le menu sur place.  Il demande ensuite à l'application serveur son menu d'activation sur place et l'insère là où les séparateurs sont.  Voici comment les menus se combinent.  Vous obtenez les menus du conteneur pour opérer sur la position du fichier et de la fenêtre, et vous obtenez les menus du serveur pour opérer sur l'élément.  
  
##  <a name="_core_toolbars_and_status_bars"></a> barres d'outils et barres d'état ;  
 Les applications serveur doivent créer une barre d'outils et stocker la bitmap dans un fichier distinct.  Les applications générées par l'Assistant stockent cette bitmap dans un fichier appelé ITOOLBAR.BMP.  La nouvelle barre d'outils remplace la barre d'outils de l'application conteneur lorsque l'élément de votre serveur est activé sur place, et doit contenir les mêmes éléments que la barre d'outils standard, mais supprime les icônes qui représentent des éléments sur les menus fichier et fenêtre.  
  
 Cette barre d'outils est chargée dans votre classe dérivée de `COleIPFrameWnd`, créée pour vous par l'assistant d'application.  La barre d'état est gérée par l'application conteneur.  Pour plus d'informations sur l'implémentation des fenêtres cadres sur place, consultez [Serveurs : Implémenter un serveur](../mfc/servers-implementing-a-server.md).  
  
## Voir aussi  
 [Menus et ressources \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Activation](../mfc/activation-cpp.md)   
 [Serveurs](../mfc/servers.md)   
 [Conteneurs](../mfc/containers.md)