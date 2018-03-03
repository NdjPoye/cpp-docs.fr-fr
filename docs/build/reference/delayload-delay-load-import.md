---
title: "-/DELAYLOAD (différer le chargement importation) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd524e72125408c6a88bea83272e18a7ef9b78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Différer le chargement de l'importation)
```  
/DELAYLOAD:dllname  
```  
  
## <a name="parameters"></a>Paramètres  
 `dllname`  
 Le nom d'une DLL dont vous voulez différer le chargement.  
  
## <a name="remarks"></a>Notes  
 Avec l'option /DELAYLOAD, la DLL spécifiée par `dllname` n'est chargée que lors du premier appel du programme à une fonction contenue dans cette DLL. Pour plus d’informations, consultez [prise en charge de l’éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md). Vous pouvez utiliser cette option autant de fois que nécessaire pour spécifier autant de DLL que vous voulez. Vous devez utiliser Delayimp.lib au moment de lier votre programme, ou vous pouvez implémenter votre propre fonction d'assistance du chargement différé.  
  
 Le [/Delay](../../build/reference/delay-delay-load-import-settings.md) option spécifie la liaison et de chargement des options pour chaque DLL à chargement différé.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le **l’éditeur de liens** dossier, sélectionnez le **entrée** page de propriétés.  
  
3.  Modifier la **chargement différé des DLL** propriété.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)