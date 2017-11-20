---
title: -/IGNOREIDL (Don &#39; les attributs de processus t dans MIDL) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.IgnoreEmbeddedIDL
- /ignoreidl
dev_langs: C++
helpviewer_keywords:
- IGNOREIDL linker option
- -IGNOREIDL linker option
- /IGNOREIDL linker option
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 52242168dc40392f28db6bd360bc6c38d50d614d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ignoreidl-don39t-process-attributes-into-midl"></a>/IGNOREIDL (Don &#39; les attributs de processus t dans MIDL)
```  
/IGNOREIDL  
```  
  
## <a name="remarks"></a>Remarques  
 L’option /IGNOREIDL spécifie que toute [attributs IDL](../../windows/idl-attributes.md) de source de code ne doit pas être traité dans un fichier .idl.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **IDL incorporé** page de propriétés.  
  
4.  Modifier la **IDL incorporé** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)   
 [/IDLOUT (nommer les fichiers de sortie MIDL)](../../build/reference/idlout-name-midl-output-files.md)   
 [/TLBOUT (nommer. Fichier TLB)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [/MIDL (spécifier les Options de ligne de commande MIDL)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Générer un programmes par attributs](../../windows/building-an-attributed-program.md)