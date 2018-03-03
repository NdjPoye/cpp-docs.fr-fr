---
title: -DELAYSIGN (signer partiellement un Assembly) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs:
- C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f67e4da2d85d94854ec0802450b41333d6577175
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Signer partiellement un assembly)
```  
/DELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 où,  
  
 NO  
 Spécifie que l’assembly ne doit pas être partiellement signé.  
  
## <a name="remarks"></a>Notes  
 Utilisez **/DELAYSIGN** si vous souhaitez uniquement placer la clé publique dans l’assembly. La valeur par défaut est **delaysign**.  
  
 Le **/DELAYSIGN** option est sans effet sauf si utilisée avec [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) ou [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 Quand vous demandez un assembly totalement signé, le compilateur hache le fichier qui contient le manifeste (métadonnées de l’assembly) et signe ce hachage avec la clé privée. La signature numérique obtenue est stockée dans le fichier qui contient le manifeste. Lorsqu’un assembly est à signature différée, l’éditeur de liens ne calcule pas et stocker la signature, mais réserve de l’espace dans le fichier afin de pouvoir ajouter ultérieurement la signature.  
  
 Par exemple, à l’aide de **/DELAYSIGN** permet à un testeur d’insérer l’assembly dans le cache global. Après le test, vous pouvez signer complètement l’assembly en plaçant la clé privée de l’assembly.  
  
 Consultez [les assemblys de nom fort (signature d’Assembly) (C + c++ / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) et [signature différée d’un Assembly](/dotnet/framework/app-domains/delay-sign-assembly) pour plus d’informations sur la signature d’un assembly.  
  
 Autres options de l’éditeur de liens qui affectent la génération de l’assembly sont :  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l’option dans le **des Options supplémentaires** boîte.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)