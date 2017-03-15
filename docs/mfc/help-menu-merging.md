---
title: "Fusion des menus Aide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menus, fusion"
  - "fusionner les menus Aide"
  - "Aide, pour les conteneurs de documents actifs"
ms.assetid: 9d615999-79ba-471a-9288-718f0c903d49
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Fusion des menus Aide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un objet est actif dans un conteneur, le protocole de fusion de menus de OLE documents fournit un contrôle complet de l'objet dans le menu de **Aide**.  Par conséquent, les rubriques d'aide du conteneur ne sont pas disponibles à moins que l'utilisateur désactive l'objet.  L'architecture de la relation contenant\-contenu de document actif examine les règles de la fusion de menus sur place afin d'autoriser le conteneur et un document actif qui est active pour partager le menu.  Les règles sont les conventions simplement supplémentaires sur quel composant possède quelle partie du menu et comment le menu partagé est créé.  
  
 La nouvelle convention est simple.  Dans les documents actifs, le menu de **Aide** deux éléments de menu de niveau supérieur organisés comme suit :  
  
 `Help`  
  
 `Container Help >`  
  
 `Object Help    >`  
  
 Par exemple, lorsqu'une section word est active dans le classeur Office, puis le menu de **Aide** apparaît comme suit :  
  
 `Help`  
  
 `Binder Help >`  
  
 `Word Help   >`  
  
 Les deux éléments de menu et les menus en cascade dans lesquels tous les éléments de menu supplémentaires spécifiques au conteneur et l'objet sont accessibles à l'utilisateur.  Les éléments affichés ici varie avec le conteneur et les objets concernés.  
  
 Pour créer ce menu fusionné de **Aide**, l'architecture de la relation contenant\-contenu de document actif OLE modifie la procédure normale de documents.  En fonction de OLE documents, la barre de menus fusionnée peut comporter six groupes de menus, à savoir **Fichier**, **Modifier**, **Conteneur**, `Object`, **Fenêtre**, **Aide**, en respectant cet ordre.  À chaque groupe, il peut y avoir zéro menus ou plus.  Les groupes **Fichier**, **Conteneur**, et **Fenêtre** appartiennent au conteneur et les groupes **Modifier**, **Object,** et **Aide** appartient à l'objet.  Lorsque l'objet souhaite réaliser la fusion de menus, il crée une barre de menus vide et la passe au conteneur.  Le conteneur insère ensuite les menus, en appelant **IOleInPlaceFrame::InsérerMenus**.  L'objet passe également une structure qui est un tableau de six LONGUES valeurs \(**OLEMENUGROUPWIDTHS**\).  Après avoir inséré les menus, le conteneur marque le nombre de menus qu'il a ajouté dans chacun de ses groupes, puis retourne.  L'objet insère les menus, prêtant l'attention au nombre de menus de chaque groupe de conteneur.  Enfin, l'objet passe la barre de menus fusionnée et la table \(contenant le nombre de menus dans chaque groupe\) vers OLE, qui retourne un handle opaque « descripteur de menu ».  Version ultérieure de l'objet qui gère la barre de menus fusionnée au conteneur, via **IOleInPlaceFrame::SetMenu**.  À ce stade, le conteneur affiche la barre de menus fusionnée et passe le handle à OLE, afin que OLE puisse distribuer des messages de menu approprié.  
  
 Dans la procédure de modification de document actif, l'objet doit d'abord initialiser les éléments de **OLEMENUGROUPWIDTHS** à zéro avant de le transmettre au conteneur.  Le conteneur exécute une insertion classique de menu à une exception près : Le conteneur insère un menu de **Aide** en tant que dernier élément et stocke la valeur 1 dans la dernière \(sixième\) entrée du tableau de **OLEMENUGROUPWIDTHS** \(autrement dit, largeur \[5\], appartenant au groupe de l'utilisation de l'objet\).  Ce menu de **Aide** ne comportera qu'un seul élément représentant un sous\-menu, **Container Help** \> le menu cascade comme décrit précédemment.  
  
 L'objet effectue ensuite le code d'insertion de menu standard, à ceci près qu'avant d'insérer le menu de **Aide**, il vérifie la sixième entrée du tableau de **OLEMENUGROUPWIDTHS**.  Si la valeur est 1 et le nom du dernier menu est **Aide** \(ou une chaîne localisée correcte\), l'objet insère le menu de **Aide** comme sous\-menu du menu de **Aide** du conteneur.  
  
 L'objet définit ensuite le sixième élément de **OLEMENUGROUPWIDTHS** à zéro et incrémente le cinquième élément par un.  Cela laisse OLE connaître le menu de **Aide** qui appartient au conteneur et les messages de menu correspondant à \(ce menu et ses sous\-menus\) doivent être routés au conteneur.  Il s'agit de la responsabilité du conteneur à transférer `WM_INITMENUPOPUP`, **WM\_SELECT**, **WM\_COMMAND**, et d'autres messages menu\- liés qui appartiennent à la partie de l'objet dans le menu de **Aide**.  Cela s'effectue en utilisant `WM_INITMENU` pour désactiver un indicateur qui indique le conteneur si l'utilisateur a accédé dans le menu de **Aide** de l'objet.  Le conteneur s'intéresse ensuite à `WM_MENUSELECT` pour l'entrée en ou la sortie d'un élément dans le menu de **Aide** que le conteneur ne peut pas ajouter lui\-même.  En entrée, cela signifie que l'utilisateur a accédé dans un menu d'objet, le conteneur définit l'indicateur « d'objet menu ? » et utilise l'état de cet indicateur pour transférer tous `WM_MENUSELECT`, `WM_INITMENUPOPUP`, et des messages de **WM\_COMMAND**, comme minimum, dans la fenêtre de l'objet. \(En sortie, le conteneur désactive l'indicateur puis traite ces derniers messages lui\-même.\) Le conteneur doit utiliser la fenêtre retournée par la fonction de **IOleInPlaceActiveObejct::GetWindow** de l'objet comme destination de ces messages.  
  
 Si l'objet est un zéro dans le sixième élément de **OLEMENUGROUPWIDTHS**, il continue selon les règles normales OLE de documents.  Cette procédure traite des conteneurs qui participent à la fusion de menus de **Aide** ainsi que celles qui ne sont pas.  
  
 Lorsque l'objet appelle **IOleInPlaceFrame::SetMenu**, avant d''afficher la barre de menus fusionnée, le conteneur vérifie si le menu de **Aide** a un sous\-menu supplémentaire, en plus de laquelle le conteneur a été inséré.  Dans ce cas, le conteneur laisse son menu **Aide** dans la barre de menus fusionnée.  Si le menu de **Aide** n'est pas un sous\-menu supplémentaire, le conteneur supprime le menu de **Aide** dans la barre de menus fusionnée.  Cette procédure traite des objets qui participent à la fusion de menus de **Aide** ainsi que celles qui ne sont pas.  
  
 Enfin, lorsqu'il est temps de désassembler le menu, l'objet supprime le menu insérer de **Aide** en plus de supprimer les autres menus insérés.  Lorsque le conteneur supprime les menus, il supprime le menu de **Aide** en plus des autres menus qu'il a inséré  
  
## Voir aussi  
 [Conteneurs de documents actifs](../mfc/active-document-containers.md)