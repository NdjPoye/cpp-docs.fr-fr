---
title: "R&#233;f&#233;rence XDCMake | Microsoft Docs"
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
  - "xdcmake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "xdcmake (programme)"
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;f&#233;rence XDCMake
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

xdcmake.exe est un programme qui compile les fichiers .xdc dans un fichier .xml.  Un fichier .xdc est créé par le compilateur Visual C\+\+ pour chaque fichier de code source lorsque le code source est compilé avec [\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) et lorsque le fichier de code source contient les commentaires de documentation marqués avec des balises XML.  
  
### Pour utiliser xdcmake.exe dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../misc/how-to-open-project-property-pages.md).  
  
2.  Ouvrez le dossier **Propriétés de configuration** .  
  
3.  Cliquez sur la page de propriétés **Commentaires de document XML** .  
  
> [!NOTE]
>  les options de xdcmake.exe à la ligne de commande diffèrent des options xdcmake.exe lorsque est utilisé dans l'environnement de développement \(pages de propriétés\).  Pour plus d'informations sur l'utilisation xdcmake.exe dans l'environnement de développement, consultez [Outil Générateur de documents XML, page de propriétés](../ide/xml-document-generator-tool-property-pages.md).  
  
## Syntaxe  
 xdcmake `input_filename options`  
  
## Paramètres  
 où :  
  
 `input_filename`  
 Le nom de fichier des fichiers .xdc utilisés comme entrée à xdcmake.exe.  Spécifiez un ou plusieurs fichiers .xdc ou utilisez \*.xdc pour utiliser tous les fichiers .xdc dans l'annuaire actuel.  
  
 `options`  
 Zéro ou plusieurs des éléments suivants :  
  
|Option|Description|  
|------------|-----------------|  
|\/? , \/help|Utilisation d'affichage pour xdcmake.exe.|  
|\/assembly :*nom de fichier*|Vous permet de spécifier la valeur de la balise d' \<assembly\> dans le fichier .xml.  Par défaut, la valeur de la balise d' \<assembly\> est identique au nom de fichier du fichier .xml.|  
|\/nologo|Supprime le message de copyright.|  
|\/out :*nom de fichier*|Vous permet de spécifier le nom du fichier .xml.  Par défaut, le nom du fichier .xml est le nom de fichier du premier fichier .xdc traité par xdcmake.exe.|  
  
## Notes  
 Visual Studio appellera xdcmake.exe automatiquement lors de la génération d'un projet.  Vous pouvez également appeler xdcmake.exe à la ligne de commande.  
  
 Consultez l' [Balises recommandées pour les commentaires de documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) pour plus d'informations sur l'ajout de commentaires de documentation des fichiers de code source.  
  
## Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)