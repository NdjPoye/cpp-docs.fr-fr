---
title: -LIBPATH (autre chemin de bibliothèque) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 452158c2767ec4f0bf30a88df17b7c01496e24e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Autre chemin de bibliothèque)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>Notes  
 où :  
  
 `dir`  
 Spécifie un chemin d’accès que l’éditeur de liens recherche avant qu’il recherche le chemin d’accès spécifié dans l’option d’environnement LIB.  
  
## <a name="remarks"></a>Notes  
 Utilisez l’option /LIBPATH pour substituer le chemin de bibliothèque d’environnement. L’éditeur de liens recherche tout d’abord dans le chemin d’accès spécifié par cette option et ensuite effectuer une recherche dans le chemin d’accès spécifié dans la variable d’environnement LIB. Vous pouvez spécifier qu’un seul répertoire pour chaque option /LIBPATH que vous entrez. Si vous souhaitez spécifier plusieurs répertoires, vous devez spécifier plusieurs options /LIBPATH. L’éditeur de liens recherche alors les répertoires spécifiés dans l’ordre.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **général** page de propriétés.  
  
4.  Modifier la **répertoires de bibliothèques supplémentaires** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)