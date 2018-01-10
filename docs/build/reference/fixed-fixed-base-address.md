---
title: -FIXE (adresse de Base fixe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
dev_langs: C++
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 201a0357d182713c473fd3e259e4e9c2a71abf4e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Adresse de base fixe)
```  
/FIXED[:NO]  
```  
  
## <a name="remarks"></a>Notes  
 Indique au système d’exploitation pour charger le programme uniquement à son adresse de base préférée. Si l’adresse de base préférée n’est pas disponible, le système d’exploitation ne charge pas le fichier. Pour plus d’informations, consultez l’article [/BASE (Adresse de base)](../../build/reference/base-base-address.md).  
  
 / Fixed : no est le paramètre par défaut pour une DLL et /FIXED est le paramètre par défaut pour n’importe quel autre type de projet.  
  
 Lorsque /FIXED est spécifié, le lien ne génère pas une section de réadressage dans le programme. Au moment de l’exécution, si le système d’exploitation ne peut pas charger le programme à l’adresse spécifiée, il émet un message d’erreur et ne charge pas le programme.  
  
 Spécifiez/FIXED : no pour générer une section de réadressage dans le programme.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **l’éditeur de liens** dossier.  
  
3.  Sélectionnez le **ligne de commande** page de propriétés.  
  
4.  Entrez le nom et la définition la **des Options supplémentaires** boîte.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)