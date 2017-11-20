---
title: "-MAP (générer fichier de mappage) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs: C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e776803ab6f7046b2db1f80899ee6e465deb399
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="map-generate-mapfile"></a>/MAP (Générer fichier de mappage)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>Remarques  
 où :  
  
 *filename*  
 Nom spécifié par l’utilisateur pour le fichier de mappage. Il remplace le nom par défaut.  
  
## <a name="remarks"></a>Remarques  
 L’option /MAP indique à l’éditeur de liens pour créer un fichier de mappage.  
  
 Par défaut, l’éditeur de liens nomme le fichier de mappage avec le nom de base du programme et l’extension .map. Le paramètre facultatif *nom de fichier* vous permet de substituer le nom par défaut pour un fichier de mappage.  
  
 Un fichier de mappage est un fichier texte qui contient les informations suivantes sur le programme lié :  
  
-   Le nom du module, qui est le nom du fichier de base  
  
-   L’horodatage de l’en-tête du fichier de programme (pas le système de fichiers)  
  
-   Une liste de groupes dans le programme, avec l’adresse de début de chaque groupe (comme *section*:*offset*), classe, nom de groupe et longueur  
  
-   Une liste de symboles publics avec chaque adresse (comme *section*:*offset*), symbole nom, adresse et le fichier .obj où le symbole est défini.  
  
-   Le point d’entrée (en tant que *section*:*offset*)  
  
 Le [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) option spécifie des informations supplémentaires à inclure dans le fichier de mappage.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **déboguer** page de propriétés.  
  
4.  Modifier la **générer fichier de mappage** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)