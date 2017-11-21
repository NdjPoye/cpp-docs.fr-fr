---
title: "-/NXCOMPAT (Compatible avec la prévention de l’exécution des données) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /NXCOMPAT
dev_langs: C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d97b1b84ef6894e4ec161dbcecef47f6b676af23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT (compatible avec la prévention de l'exécution des données)
Indique qu’un fichier exécutable a été testé pour être compatible avec la fonctionnalité de prévention de l’exécution des données Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/NXCOMPAT[:NO]  
```  
  
## <a name="remarks"></a>Remarques  
 Par défaut, **/NXCOMPAT** sur.  
  
 **Sa** peut être utilisé pour spécifier explicitement un fichier exécutable comme étant incompatible avec la prévention de l’exécution des données.  
  
 Pour plus d’informations sur la prévention de l’exécution des données, consultez les articles suivants :  
  
-   [Une description détaillée de la fonctionnalité de prévention de l’exécution des données (PED)](http://go.microsoft.com/fwlink/?LinkID=157771) sur le site Web de la prise en charge et de Microsoft Help  
  
-   [Prévention de l’exécution des données](http://go.microsoft.com/fwlink/?LinkID=157770) sur le site Web MSDN  
  
-   [Prévention de l’exécution des données (Windows Embedded)](http://go.microsoft.com/fwlink/?LinkID=157768) sur le site Web MSDN  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Pour définir cette option d'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur la page de propriétés **Ligne de commande** .  
  
4.  Tapez l’option dans le **des Options supplémentaires** boîte.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)