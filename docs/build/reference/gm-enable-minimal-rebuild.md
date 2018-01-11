---
title: "-Gm (activer la régénération minimale) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs: C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bc9ff065de2b83d50b6fa905fcc6d1123dbe829
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (Activer la régénération minimale)
Permet une régénération minimale, qui détermine si les fichiers sources C++ qui incluent des définitions de classe C++ modifiées (stockées dans des fichiers d'en-tête (.h)) doivent être recompilés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Gm  
```  
  
## <a name="remarks"></a>Notes  
 Le compilateur stocke des informations sur les dépendances entre les fichiers sources et les définitions de classe dans le fichier .idb du projet au cours de la première compilation. (Les informations de dépendance indiquent quel fichier source dépend de la définition de classe, et quel fichier .h la définition se trouve dans.) Les compilations ultérieures utilisent les informations stockées dans le fichier .idb pour déterminer si un fichier source doit être compilé, même s’il comprend un fichier .h modifié.  
  
> [!NOTE]
>  Une régénération minimale s'appuie sur des définitions de classe qui ne changent pas entre les fichiers Include. Les définitions de classe doivent être globales pour un projet (il doit exister une seule définition d'une classe donnée), car les informations sur les dépendances dans le fichier .idb sont créées pour le projet entier. Si vous possédez plusieurs définitions pour une classe dans votre projet, désactivez la régénération minimale.  
  
 Étant donné que l’éditeur de liens incrémentiel ne prend pas en charge les métadonnées Windows incluses dans les fichiers .obj à l’aide de la [/ZW (Compilation Windows Runtime)](../../build/reference/zw-windows-runtime-compilation.md) option, le **/Gm** option n’est pas compatible avec  **/ZW**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **C/C++** .  
  
3.  Cliquez sur le **génération de Code** page de propriétés.  
  
4.  Modifier la **activer la régénération minimale** propriété.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)