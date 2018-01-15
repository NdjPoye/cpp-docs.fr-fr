---
title: "-SWAPRUN (charge l’utilisation de la sortie de l’éditeur de liens pour le fichier d’échange) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
dev_langs: C++
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3b6829a20e80ab8548460205169e1cd258694e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (Charger la sortie de l'Éditeur de liens dans le fichier d'échange)
```  
/SWAPRUN:{NET|CD}  
```  
  
## <a name="remarks"></a>Notes  
 Cette option indique le système d’exploitation pour la première copie de l’éditeur de liens de sortie dans un fichier d’échange, puis exécute l’image à partir de là. Il s’agit d’une fonctionnalité de Windows NT 4.0 (et versions ultérieure).  
  
 Si NET est spécifié, le système d’exploitation sera tout d’abord copier l’image binaire du réseau dans un fichier d’échange et chargez-le à partir de là. Cette option est utile pour les applications en cours d’exécution sur le réseau. Lorsque le CD est spécifié, le système d’exploitation sera copier l’image sur un disque amovible sur un fichier d’échange, puis son chargement.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le **l’éditeur de liens** dossier.  
  
3.  Cliquez sur le **système** page de propriétés.  
  
4.  Modifier l’une des propriétés suivantes :  
  
    -   **Exécuter l’échange à partir du CD**  
  
    -   **Exécuter l’échange à partir du réseau**  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)