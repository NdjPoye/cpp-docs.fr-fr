---
title: "-/CLRIMAGETYPE (spécifier le Type d’Image CLR) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs: C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d8edd6c9e62456e54ac6228f25d7f923a6813c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Spécifier le type d'une image CLR)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Notes  
 L’éditeur de liens accepte des objets natifs, et également MSIL objets qui sont compilées à l’aide de [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), / CLR : pure ou/CLR : safe. Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015. Lorsque des objets mixtes dans la même build sont transmis, la vérifiabilité du fichier de sortie résultant est, par défaut, égale à niveau le plus bas de vérifiabilité des modules d’entrée. Par exemple, si vous passez un coffre-fort et un module de code à l’éditeur de liens, le fichier de sortie sera pur. Si vous passez une image native et une image en mode mixte (compilée à l’aide de **/CLR**), l’image résultante est une image en mode mixte.  
  
 Vous pouvez utiliser CLRIMAGETYPE pour spécifier un niveau inférieur de vérifiabilité, si c’est ce dont vous avez besoin.  
  
 Dans .NET 4.5, CLRIMAGETYPE prend en charge une option SAFE32BITPREFERRED. Cela permet de définir, dans l’en-tête PE de l’image : indicateurs qui indiquent que les objets MSIL sont sécurisés et peuvent être exécutent sur toutes les plateformes, mais que les environnements d’exécution de 32 bits sont par défaut. Cette option permet à une application de s’exécuter sur les plateformes ARM et indique également qu’il doit s’exécuter sous WOW64 sur les systèmes d’exploitation 64 bits au lieu d’utiliser l’environnement d’exécution de 64 bits.  
  
 Lorsqu’un .exe qui a été compilé à l’aide de **/CLR** ou **/CLR : pure** est exécuté sur un système d’exploitation 64 bits, l’application est exécutée sous WOW64, ce qui permet à une application 32 bits pour s’exécuter sur un système d’exploitation de 64 bits. Par défaut, un .exe compilé à l’aide de **/CLR : safe** est exécuté sous la prise en charge de 64 bits du système d’exploitation. Toutefois, il est possible que votre application safe charge un composant 32 bits. Dans ce cas, une image safe s’exécutant sous la prise en charge de 64 bits du système d’exploitation échoue lors du chargement de l’application 32 bits. Pour vous assurer qu’une image safe continuera à s’exécuter lors du chargement d’un composant 32 bits sur un système d’exploitation de 64 bits, utilisez l’option /CLRIMAGETYPE:SAFE32BITPREFERRED. Si votre code ne doit pas s’exécuter sur les plateformes ARM, vous pouvez spécifier le CLRIMAGETYPE : PURE permettant de modifier les métadonnées (.corflags), le marquage qu’elles s’exécutent sous WOW64 (et en substituant votre propre symbole d’entrée) :  
  
 **cl /clr:safe t.cpp /link /clrimagetype:pure /entry:?main@@$$HYMHXZ /subsystem:console**  
  
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