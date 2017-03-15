---
title: "Menus et ressources&#160;: ajouts de conteneurs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDP_OLE_INIT_FAILED"
  - "IDP_FAILED_TO_CREATE"
  - "VK_ESCAPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tables d'accélérateurs (C++), applications conteneur"
  - "table d'accélérateurs d'application (C++)"
  - "CONTAIN (didacticiel)"
  - "IDP_FAILED_TO_CREATE (macro)"
  - "IDP_OLE_INIT_FAILED (macro)"
  - "Links (éléments de menu)"
  - "conteneurs OLE, menus et ressources"
  - "édition visuelle, menus et ressources d'applications"
  - "VK_ESCAPE (touche)"
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Menus et ressources&#160;: ajouts de conteneurs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique les modifications qui doivent être apportées aux menus et d'autres ressources dans une application conteneur de modification.  
  
 Dans les applications conteneur, deux types de modifications doivent être effectuées : modification des ressources existantes pour prendre en charge la modification sur place OLE et l'ajout de nouvelles ressources utilisées pour l'activation sur place.  Si vous utilisez l'Assistant Application pour créer votre application conteneur, ces étapes sont effectuées pour vous, mais elles peuvent nécessiter de la personnalisation.  
  
 Si vous n'utilisez pas l'Assistant Application, vous pouvez examiner OCLIENT.RC, le script de ressources pour l'exemple d'application de OCLIENT, pour voir comment ces modifications sont implémentées.  Consultez l'exemple MFC OLE [OCLIENT](../top/visual-cpp-samples.md).  
  
 Les rubriques traitées dans cet article sont les suivantes :  
  
-   [Ajouts au menu de conteneur](#_core_container_menu_additions)  
  
-   [Ajouts à la table des accélérateurs](#_core_container_application_accelerator_table_additions)  
  
-   [Ajout aux chaînes](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a> Ajouts au menu de conteneur  
 Vous devez ajouter les éléments suivants dans le menu Edition :  
  
|Élément|Objectif|  
|-------------|--------------|  
|**Insérer un nouvel objet**|Ouvre la boîte de dialogue d'insertion d'objet OLE pour insérer un élément lié ou incorporé dans le document.|  
|**Coller un lien**|Colle un lien vers l'élément dans le presse\-papiers dans le document.|  
|**Verbe OLE**|Appelle le verbe principal de l'élément sélectionné.  Le texte de l'élément de menu change pour refléter le verbe principal de l'élément sélectionné.|  
|**Liens**|Ouvre la boîte de dialogue d'édition de liens OLE pour modifier les éléments liés existants.|  
  
 En plus des modifications indiquées de cet article, votre fichier source doit inclure AFXOLECL.RC, qui est requis pour l'implémentation de la bibliothèque MFC.  Insérer un nouvel objet est le seul ajout nécessaire au menu.  D'autres éléments peuvent être ajoutés, mais ces listés ici sont les plus courantes.  
  
 Vous devez créer un nouveau menu pour votre application conteneur si vous voulez prendre en charge l'activation sur place des éléments contenus.  Ce menu comprend le même Fichier menu et les menus contextuels d'affichage utilisés lorsque des fichiers sont ouverts, mais il possède deux séparateurs placés entre eux.  Les séparateurs sont utilisés pour indiquer où l'élément \(application\) du serveur \(composant\) doit rechercher les menus une fois activé en place.  Pour plus d'informations sur cette technique de fusion de menus, consultez [Menus et ressources : Fusion de menus](../mfc/menus-and-resources-menu-merging.md).  
  
##  <a name="_core_container_application_accelerator_table_additions"></a> Ajouts aux tables des accélérateurs d'application conteneur  
 Les petites modifications aux ressources table des accélérateurs d'une application conteneur sont nécessaires si vous prenez en charge l'activation sur place.  La première modification permet à l'utilisateur d'appuyer sur la touche ESCAPE \(ESC\) pour quitter le mode de modification sur place.  Ajoutez l'entrée suivante à la table principale des accélérateurs :  
  
|ID|Clé|Type|  
|--------|---------|----------|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
 La deuxième modification consiste à créer une nouvelle table des accélérateurs qui correspond à la nouvelle ressource menu créée pour l'activation sur place.  Cette table a des entrées pour les menus Fichier et Fenêtre en plus de l'entrée **VK\_ESCAPE** ci\-dessus.  L'exemple suivant est la table des accélérateurs créée pour l'activation sur place dans l'exemple MFC [CONTAINER](../top/visual-cpp-samples.md) :  
  
|ID|Clé|Type|  
|--------|---------|----------|  
|`ID_FILE_NEW`|CTRL\+N|**VIRTKEY**|  
|`ID_FILE_OPEN`|CTRL\+O|**VIRTKEY**|  
|**ID\_FILE\_SAVE**|CTRL\+S|**VIRTKEY**|  
|**ID\_FILE\_PRINT**|CTRL\+P|**VIRTKEY**|  
|**ID\_NEXT\_PANE**|VK\_F6|**VIRTKEY**|  
|**ID\_PREV\_PANE**|SHIFT\+VK\_F6|**VIRTKEY**|  
|**ID\_CANCEL\_EDIT\_CNTR**|VK\_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a> Ajouts de chaînes pour les applications conteneur  
 La plupart des modifications apportées aux tables de chaînes pour les applications conteneur correspondent à des éléments de menu supplémentaires mentionnés dans [Ajouts au menu de conteneur](#_core_container_menu_additions).  Ils fournissent le texte affiché dans la barre d'état lorsque chaque élément de menu s'affiche.  Par exemple, voici les entrées de chaînes que l'Assistant d'Application génère :  
  
|ID|String|  
|--------|------------|  
|**IDP\_OLE\_INIT\_FAILED**|Échec de l'initialisation d'OLE.  Assurez\-vous que vous utilisez la bonne version des bibliothèques OLE.|  
|**IDP\_FAILED\_TO\_CREATE**|Échec de création d'un objet.  Assurez\-vous que l'objet est entré dans le registre système.|  
  
## Voir aussi  
 [Menus et ressources \(OLE\)](../mfc/menus-and-resources-ole.md)   
 [Menus et ressources : ajouts de serveurs](../mfc/menus-and-resources-server-additions.md)