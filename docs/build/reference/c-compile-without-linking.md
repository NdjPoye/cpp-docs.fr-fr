---
title: -c (compiler sans liaison) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /c
dev_langs:
- C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 112e063af9c56ead8ae7e8f59fe88853ff55f7b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="c-compile-without-linking"></a>/c (Compiler sans liaison)
Empêche l’appel automatique à LINK.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/c  
```  
  
## <a name="remarks"></a>Notes  
 La compilation avec **/c** crée des fichiers .obj uniquement. Vous devez appeler explicitement des lien avec les fichiers appropriés et les options permettant d’effectuer la phase de liaison de la build.  
  
 Tout projet interne créé dans l’environnement de développement utilise les **/c** option par défaut.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
-   Cette option n’est pas disponible dans l’environnement de développement.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Pour définir cette option du compilateur par programmation, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.  
  
## <a name="example"></a>Exemple  
 La ligne de commande suivante crée les fichiers objets FIRST.obj et SECOND.obj. THIRD.obj est ignoré.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Pour créer un fichier exécutable, vous devez appeler LINK :  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)