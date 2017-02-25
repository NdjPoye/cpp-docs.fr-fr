---
title: "Outil G&#233;n&#233;rateur de documents XML, page de propri&#233;t&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCXDCMakeTool.ValidateIntelliSense"
  - "VC.Project.VCXDCMakeTool.SuppressStartupBanner"
  - "VC.Project.VCXDCMakeTool.DocumentLibraryDependencies"
  - "VC.Project.VCXDCMakeTool.OutputDocumentFile"
  - "VC.Project.VCXDCMakeTool.AdditionalDocumentFiles"
dev_langs: 
  - "C++"
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Outil G&#233;n&#233;rateur de documents XML, page de propri&#233;t&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La page de propriétés Outil Générateur de documents XML expose les fonctionnalités de xdcmake.exe.  xdcmake.exe fusionne des fichiers .xdc dans un fichier .xml lorsque votre code source contient des commentaires sur la documentation et que [\/doc \(Traiter les commentaires de documentation\)](../build/reference/doc-process-documentation-comments-c-cpp.md) est spécifié.  Consultez [Balises recommandées pour commentaires de documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) pour plus d'informations sur l'ajout de commentaires de documentation au code source.  
  
> [!NOTE]
>  les options du fichier exécutable xdcmake.exe dans l'environnement de développement \(pages de propriétés\) diffèrent de ses options à partir de la ligne de commande.  Pour plus d'informations sur l'utilisation de xdcmake.exe depuis la ligne de commande, consultez [Référence XDCMake](../ide/xdcmake-reference.md).  
  
## Liste UIElement  
 **Suppression de la bannière de démarrage**  
 Supprime le message de copyright.  
  
 **Fichiers de document supplémentaires**  
 Répertoires supplémentaires dans lesquels vous voulez que le système de projet recherche des fichiers .xdc.  xdcmake recherchera toujours des fichiers .xdc générés par le projet.  Plusieurs répertoires peuvent être spécifiés.  
  
 **Fichier de document de sortie**  
 Nom et emplacement du répertoire du fichier de sortie .xml.  Consultez [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md) pour plus d'informations sur l'utilisation de macros pour spécifier des emplacements de répertoires.  
  
 **Dépendances de bibliothèque de documents**  
 Si votre projet présente une dépendance à un projet .lib dans la solution, vous pouvez traiter des fichiers .xdc à partir du projet .lib dans les fichiers .xml du projet actuel.  
  
## Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)