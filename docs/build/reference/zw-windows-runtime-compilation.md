---
title: -ZW (Compilation Windows Runtime) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
dev_langs: C++
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 75f46c2eaaa42f473e02bc553dd06b86cd5bbc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="zw-windows-runtime-compilation"></a>/ZW (compilation Windows Runtime)
Compile le code source pour prendre en charge [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]) pour la création d'applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  
  
 Lorsque vous utilisez **/ZW** pour compiler, spécifiez toujours **/EHsc** également.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
/ZW /EHsc  
/ZW:nostdlib /EHsc  
```  
  
## <a name="arguments"></a>Arguments  
 nostdlib  
 Indique que Platform.winmd, Windows.Foundation.winmd et les autres fichiers de métadonnées Windows par défaut (.winmd) ne sont pas inclus automatiquement dans la compilation. Au lieu de cela, vous devez utiliser le [/FU (nom forcé #using fichier)](../../build/reference/fu-name-forced-hash-using-file.md) option du compilateur pour spécifier explicitement les fichiers de métadonnées Windows.  
  
## <a name="remarks"></a>Notes  
 Lorsque vous spécifiez la **/ZW** option, le compilateur prend en charge ces fonctionnalités :  
  
-   Les fichiers de métadonnées requises, espaces de noms, types de données et fonctions que votre application a besoin pour s’exécuter dans le Windows Runtime.  
  
-   Le décompte des objets Windows Runtime et automatique de rejet d’un objet lorsque son décompte de références atteint zéro.  
  
 Étant donné que l’éditeur de liens incrémentiel ne prend pas en charge les métadonnées Windows incluses dans les fichiers .obj à l’aide de la **/ZW** option, le [/Gm (activer la régénération minimale)](../../build/reference/gm-enable-minimal-rebuild.md) option n’est pas compatible avec **/ZW** .  
  
 Pour plus d’informations, consultez [référence du langage Visual C++](../../cppcx/visual-c-language-reference-c-cx.md).  
  
## <a name="requirements"></a>Spécifications  
  
## <a name="see-also"></a>Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)