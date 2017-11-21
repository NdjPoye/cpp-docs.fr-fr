---
title: -Qsafe_fp_loads | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f79a73565a78c8972d9d77b809cd77d774b821f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads
Nécessite des instructions de déplacement entier pour les valeurs à virgule flottante et désactive certaines optimisations à virgule flottante de charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/Qsafe_fp_loads  
```  
  
## <a name="remarks"></a>Remarques  
 **/ Qsafe_fp_loads** est disponible uniquement dans les compilateurs qui ciblent x86 ; il n’est pas disponible dans les compilateurs qui ciblent x64 ou ARM.  
  
 **/ Qsafe_fp_loads** inscrit de force le compilateur à utiliser des instructions de déplacement entier au lieu des instructions de déplacement à virgule flottante pour déplacer des données entre la mémoire et MMX. Cette option désactive également le Registre de l’optimisation de charge pour les valeurs à virgule flottante qui peut être chargée dans plusieurs chemins d’accès de contrôle lorsque la valeur peut provoquer une exception lors du chargement, par exemple, une valeur NaN.  
  
 Cette option est remplacée par [/fp : sauf](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** spécifie un sous-ensemble du comportement du compilateur spécifié par **/fp : sauf**.  
  
 **/ Qsafe_fp_loads** n’est pas compatible avec [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) et [Fast](../../build/reference/fp-specify-floating-point-behavior.md). Pour plus d’informations sur les options de compilateur point flottant, consultez [/fp (spécifier du comportement de nombres à virgule flottante)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **C/C++** dossier.  
  
3.  Sélectionnez le **ligne de commande** page de propriétés.  
  
4.  Tapez l'option de compilateur dans la zone **Options supplémentaires** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [/Q (opérations de bas niveau), options](../../build/reference/q-options-low-level-operations.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)