---
title: XML Document Generator Tool Property Pages | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCXDCMakeTool.ValidateIntelliSense
- VC.Project.VCXDCMakeTool.SuppressStartupBanner
- VC.Project.VCXDCMakeTool.DocumentLibraryDependencies
- VC.Project.VCXDCMakeTool.OutputDocumentFile
- VC.Project.VCXDCMakeTool.AdditionalDocumentFiles
dev_langs: C++
ms.assetid: 645912b5-197a-4c36-ba58-64df09444ca0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc09dafc0f07bc16a11dd255419440b6464456c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="xml-document-generator-tool-property-pages"></a>Outil Générateur de documents XML, page de propriétés
La page de propriétés outil Générateur de documents XML expose les fonctionnalités de xdcmake.exe. xdcmake.exe fusionne des fichiers .xdc dans un fichier .xml lorsque votre code source contient des commentaires de documentation et [/doc (traiter les commentaires de Documentation) (C/C++)](../build/reference/doc-process-documentation-comments-c-cpp.md) est spécifié,. Consultez [balises recommandées pour commentaires de Documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) pour plus d’informations sur l’ajout de commentaires de documentation au code source.  
  
> [!NOTE]
>  options xdcmake.exe dans l’environnement de développement (pages de propriétés) diffèrent des options lorsque xdcmake.exe est utilisé à la ligne de commande. Pour plus d’informations sur l’utilisation de xdcmake.exe depuis la ligne de commande, consultez [XDCMake référence](../ide/xdcmake-reference.md).  
  
## <a name="uielement-list"></a>Liste des éléments d’interface  
 **Suppression de la bannière de démarrage**  
 Supprimer le message de copyright.  
  
 **Fichiers de Document supplémentaires**  
 Répertoires supplémentaires dans lesquels vous souhaitez le système de projet pour rechercher des fichiers .xdc. xdcmake recherchera toujours des fichiers .xdc générés par le projet. Plusieurs répertoires peuvent être spécifiés.  
  
 **Fichier de Document de sortie**  
 Le nom et répertoire l’emplacement du fichier de sortie .xml. Consultez [Macros commun pour les commandes de génération et les propriétés](../ide/common-macros-for-build-commands-and-properties.md) pour plus d’informations sur l’utilisation de macros pour spécifier des emplacements de répertoire.  
  
 **Dépendances de bibliothèque de documents**  
 Si votre projet a une dépendance sur un projet .lib dans la solution, vous pouvez traiter des fichiers .xdc à partir du projet .lib dans les fichiers .xml pour le projet actuel.  
  
## <a name="see-also"></a>Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)   
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)