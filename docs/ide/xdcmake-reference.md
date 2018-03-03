---
title: "Référence XDCMake | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea635d701b4dea2471067072083d9568f11f3d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="xdcmake-reference"></a>Référence XDCMake
xdcmake.exe est un programme qui compile les fichiers .xdc dans un fichier .xml. Un fichier .xdc est créé par le compilateur Visual C++ pour chaque fichier de code source lorsque le code source est compilé avec [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) et lorsque le fichier de code source contient des commentaires de documentation marqués avec des balises XML.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Utilisation de xdcmake.exe dans l’environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
2.  Ouvrez le **propriétés de Configuration** dossier.  
  
3.  Cliquez sur le **commentaires de Document XML** page de propriétés.  
  
> [!NOTE]
>  des options au niveau de la ligne de commande xdcmake.exe diffèrent des options lorsque xdcmake.exe est utilisé dans l’environnement de développement (pages de propriétés). Pour plus d’informations sur l’utilisation de xdcmake.exe dans l’environnement de développement, consultez [XML Document Generator Tool Property Pages](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Syntaxe  
 xdcmake`input_filename options`  
  
## <a name="parameters"></a>Paramètres  
 où :  
  
 `input_filename`  
 Le nom de fichier des fichiers .xdc utilisés comme entrée pour xdcmake.exe. Spécifiez un ou plusieurs fichiers .xdc ou *.xdc permet d’utiliser tous les fichiers .xdc dans le répertoire actif.  
  
 `options`  
 Zéro ou plusieurs des opérations suivantes :  
  
|Option|Description|  
|------------|-----------------|  
|/ ?, /Help|Afficher l’aide pour xdcmake.exe.|  
|/ assembly :*nom de fichier*|Vous permet de spécifier la valeur de la \<assembly > balise dans le fichier .xml.  Par défaut, la valeur de la \<assembly > balise est le même que le nom de fichier du fichier .xml.|  
|/nologo|Supprimer le message de copyright.|  
|/ out :*nom de fichier*|Permet de spécifier le nom du fichier .xml.  Par défaut, le nom du fichier .xml est le nom de fichier du premier fichier .xdc traité par xdcmake.exe.|  
  
## <a name="remarks"></a>Notes  
 Visual Studio appelle xdcmake.exe automatiquement lors de la génération d’un projet. Vous pouvez également appeler xdcmake.exe à la ligne de commande.  
  
 Consultez [balises recommandées pour commentaires de Documentation](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) pour plus d’informations sur l’ajout de commentaires de documentation pour les fichiers de code source.  
  
## <a name="see-also"></a>Voir aussi  
 [Documentation XML](../ide/xml-documentation-visual-cpp.md)