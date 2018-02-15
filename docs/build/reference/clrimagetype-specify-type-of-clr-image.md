---
title: "-/CLRIMAGETYPE (spécifier le Type d’Image CLR) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8de8abb1602499cea0b1412d4199ea54b3bf601
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Spécifier le type d'une image CLR)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Notes  
 L’éditeur de liens accepte des objets natifs, et également MSIL objets qui sont compilées à l’aide de [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). Le **/CLR : pure** et **/CLR : safe** options du compilateur ont été déconseillées dans Visual Studio 2015. Lorsque des objets mixtes dans la même build sont transmis, la vérifiabilité du fichier de sortie résultant est, par défaut, égale à niveau le plus bas de vérifiabilité des modules d’entrée. Par exemple, si vous passez une image native et une image en mode mixte (compilée à l’aide de **/CLR**), l’image résultante est une image en mode mixte.  
  
 Vous pouvez utiliser CLRIMAGETYPE pour spécifier un niveau inférieur de vérifiabilité, si c’est ce dont vous avez besoin.  
  
 Pour plus d’informations sur la façon de déterminer le type d’image CLR d’un fichier, consultez [/CLRHEADER](../../build/reference/clrheader.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Développez le **propriétés de Configuration** nœud.  
  
3.  Développez le **l’éditeur de liens** nœud.  
  
4.  Sélectionnez le **avancé** page de propriétés.  
  
5.  Modifier la **Type d’Image CLR** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)