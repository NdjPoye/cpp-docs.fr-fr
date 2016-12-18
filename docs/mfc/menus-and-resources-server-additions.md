---
title: "Menus et ressources&#160;: ajouts de serveurs | Microsoft Docs"
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
  - "IDP_OLE_INIT_FAILED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables d'accélérateurs (C++), applications serveur"
  - "IDP_OLE_INIT_FAILED (macro)"
  - "OLE (échec de l'initialisation)"
  - "applications serveur OLE, menus et ressources"
  - "OLE (serveurs d'édition visuelle)"
  - "ressources (MFC), applications serveur"
  - "applications serveur, table d'accélérateurs"
  - "applications serveur, OLE (menus et ressources)"
  - "serveurs, ajouts de menus"
  - "modification de chaînes, applications d'édition visuelle"
  - "tables de chaînes, applications d'édition visuelle"
  - "édition visuelle, menus et ressources d'applications"
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Menus et ressources&#160;: ajouts de serveurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les modifications qui doivent être apportées aux menus et d'autres ressources dans une application de serveur \(composant\) de modification.  Une application serveur nécessite de nombreux ajouts à la structure du menu et d'autres ressources car elle peut être démarrée dans l'un des trois modes : autonome, incorporé, ou en place.  Comme décrit dans l'article de [Menus et des ressources \(OLE DB\)](../mfc/menus-and-resources-ole.md), il existe quatre ensembles de menus.  Les quatre sont utilisés pour une application de serveur complète MDI, tandis que seuls trois sont utilisés pour un miniserver.  L'Application créera la disposition du menu nécessaire pour le type de serveur de votre choix.  De la personnalisation peut être nécessaire.  
  
 Si vous n'utilisez pas l'application wizard, vous devriez consulter HIERSVR.RC, le script de ressource pour l'application exemple MFC [HIERSVR](../top/visual-cpp-samples.md), pour voir comment les modifications ont été implémentées.  
  
 Les rubriques traitées dans cet article sont les suivantes :  
  
-   [Ajouts de menu de serveur](#_core_server_menu_additions)  
  
-   [Ajouts à la table des accélérateurs](#_core_server_application_accelerator_table_additions)  
  
-   [Ajout aux chaînes](../mfc/menus-and-resources-container-additions.md)  
  
-   [Ajouts de Miniserver](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a> Ajouts de menu de serveur  
 Les applications de serveur \(composant\) doivent avoir des ressources menu ajoutées pour prendre en charge OLE la modification sur place.  Les menus utilisés lorsque l'application est exécutée en mode autonome ne doivent pas être modifiés, mais vous devez ajouter deux nouvelles ressources menu avant de générer l'application : un pour prendre en charge l'activation sur place et un pour prendre en charge le serveur qui est entièrement ouvert.  Les deux menu ressources utilisées par la valeur FULL et des applications de miniserver.  
  
-   Pour prendre en charge l'activation sur place, vous devez créer une ressource menu qui est très similaire à la ressource menu utilisée lors d'une exécution en mode autonome.  La différence dans ce menu est que les éléments de fichiers et de fenêtre \(et tous les autres éléments de menu qui sont liés à l'application, et non les données\) sont manquants.  L'application conteneur fournit ces éléments de menu.  Pour plus d'informations sur, et un exemple, de cette technique de fusion de menus, consultez l'article [Menus et de ressources : Fusion de menus](../mfc/menus-and-resources-menu-merging.md).  
  
-   Pour prendre en charge l'activation entièrement ouverte, vous devez créer une ressource presque identique dans la ressource menu utilisée lorsqu'il est exécuté en mode autonome.  La seule modification de cette ressource menu est que certains éléments sont reformulés pour refléter le fait que le serveur fonctionne sur un élément incorporé dans un document composite.  
  
 En plus des modifications indiquées de cet article, votre fichier source doit inclure AFXOLECL.RC, qui est requis pour l'implémentation de la bibliothèque MFC.  Ce fichier se trouve dans MFC\\inclut le sous\-répertoire.  
  
##  <a name="_core_server_application_accelerator_table_additions"></a> Ajouts aux tables des accélérateurs d'application serveur  
 Deux nouvelles ressources table des accélérateurs doivent être ajoutées aux applications serveur ; elles correspondent directement aux nouvelles ressources menu décrites précédemment.  La première table des accélérateurs est utilisée lorsque l'application serveur est activée sur l'emplacement.  Elle se compose de toutes les entrées dans la table des accélérateurs de la vue à l'exception de ceux liée au fichier et des menus Fenêtre.  
  
 La deuxième table est presque une copie exacte de la table des accélérateurs de la vue.  Les modifications en parallèle différences de faits dans le menu entièrement ouvert mentionnés dans [Ajouts de menu de serveur](#_core_server_menu_additions).  
  
 Pour obtenir un exemple de ces modifications des tables des accélérateurs, comparez les tables des accélérateurs **IDR\_HIERSVRTYPE\_SRVR\_IP** et **IDR\_HIERSVRTYPE\_SRVR\_EMB** avec **IDR\_MAINFRAME** dans le fichier de HIERSVR.RC inclus dans l'exemple de liaison et incorporation d'objets MFC [HIERSVR](../top/visual-cpp-samples.md).  Des accélérateurs de fichiers et de fenêtre sont absents de la table dans l'emplacement et nécessitent des copies de ces derniers sont dans la table incorporée.  
  
##  <a name="_core_string_table_additions_for_server_applications"></a> Ajouts de chaînes pour les applications serveur  
 Un seul ajout de chaînes est nécessaire dans une application serveur — chaîne pour indiquer que la OLE initialisation a échoué.  Par exemple, voici l'entrée de table de caractères que l'Assistant d'Application génère :  
  
|ID|String|  
|--------|------------|  
|**IDP\_OLE\_INIT\_FAILED**|Échec de l'initialisation d'OLE.  Assurez\-vous que vous utilisez la bonne version des bibliothèques OLE.|  
  
##  <a name="_core_mini.2d.server_additions"></a> Ajouts de Miniserver  
 Les mêmes ajouts s'appliquent aux miniservers en tant que ceux répertoriés ci\-dessus pour les serveurs entiers.  Étant donné qu'un miniserver ne peut pas être exécuté en mode autonome, son menu principal est beaucoup plus petit.  Dans le menu créé par l'Application a un menu Fichier, qui contient uniquement les éléments Quitter et A propos.  Les menus et accélérateurs intégrés et imbriqués sur l'emplacement pour les miniservers sont les mêmes que celles pour les serveurs entiers.  
  
## Voir aussi  
 [Menus et ressources \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Menus et ressource : fusion de menus](../mfc/menus-and-resources-menu-merging.md)