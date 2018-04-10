---
title: -PDBSTRIPPED (suppression des symboles privés) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /pdbstripped
- VC.Project.VCLinkerTool.StripPrivateSymbols
dev_langs:
- C++
helpviewer_keywords:
- /PDBSTRIPPED linker option
- -PDBSTRIPPED linker option
- .pdb files, stripping private symbols
- PDB files, stripping private symbols
- PDBSTRIPPED linker option
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ff124dec52a77ed5bf35d2454f95854ebea5eea0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pdbstripped-strip-private-symbols"></a>/PDBSTRIPPED (Supprimer les symboles privés)
```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 *pdb_file_name*  
 Nom spécifié par l’utilisateur pour la base de données du programme supprimée (PDB) qui crée de l’éditeur de liens.  
  
## <a name="remarks"></a>Notes  
 L’option /PDBSTRIPPED crée un second fichier (PDB) de la base de données de programme lorsque vous générez votre image de programme avec toute du compilateur ou l’éditeur de liens générant un fichier PDB ([/DEBUG](../../build/reference/debug-generate-debug-info.md), [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), /Zd ou /Zi). Ce second fichier PDB omet les symboles que vous ne souhaitez pas envoyer à vos clients. Le second fichier PDB ne contient que :  
  
-   Symboles publics  
  
-   La liste des fichiers objets et les parties de l’exécutable auquel elles contribuent  
  
-   Enregistrements de débogage (FPO) de l’optimisation pointeur frame utilisées pour parcourir la pile  
  
 Le fichier PDB supprimé ne contiendra pas :  
  
-   Informations de type  
  
-   Informations de numéro de ligne  
  
-   Symboles CodeView des fichiers par objet tels que ceux des fonctions, des variables locales et des données statiques  
  
 Le fichier PDB complet sera toujours être généré lorsque vous utilisez /PDBSTRIPPED.  
  
 Si vous ne créez pas un fichier PDB, /PDBSTRIPPED est ignoré.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **déboguer** page de propriétés.  
  
4.  Modifier la **suppression des symboles privés** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)