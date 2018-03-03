---
title: "-PDB (base de données du programme utilisation) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /pdb
- VC.Project.VCLinkerTool.ProgramDatabaseFile
dev_langs:
- C++
helpviewer_keywords:
- -PDB linker option
- /PDB linker option
- PDB linker option
- PDB files, creating
- .pdb files, creating
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b8b255e88a199397463d26d408d425234571552
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pdb-use-program-database"></a>/PDB (Utiliser la base de données du programme)
```  
/PDB:filename  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 *filename*  
 Nom spécifié par l’utilisateur pour la base de données du programme (PDB) qui crée de l’éditeur de liens. Il remplace le nom par défaut.  
  
## <a name="remarks"></a>Notes  
 Par défaut, lorsque [/DEBUG](../../build/reference/debug-generate-debug-info.md) est spécifié, l’éditeur de liens crée une base de données du programme (PDB) qui contient des informations de débogage. Nom de fichier par défaut pour le fichier PDB est le nom de base du programme et l’extension .pdb.  
  
 Utilisez/PDB :*nom de fichier* pour spécifier le nom du fichier PDB. Si /DEBUG n’est pas spécifié, l’option /PDB est ignorée.  
  
 Un fichier PDB peut être jusqu'à 2 Go.  
  
 Pour plus d’informations, consultez [fichiers .pdb en tant qu’entrée de l’éditeur de liens](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **déboguer** page de propriétés.  
  
4.  Modifier la **générer un fichier de base de données de programme** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)