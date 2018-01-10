---
title: -OPT (optimisations) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OptimizeReferences
- /opt
- VC.Project.VCLinkerTool.OptimizeForWindows98
- VC.Project.VCLinkerTool.EnableCOMDATFolding
- VC.Project.VCLinkerTool.OptimizeFolding
- VC.Project.VCLinkerTool.FoldingIterations
- VC.Project.VCLinkerTool.OptimizeFoldingIterations
dev_langs: C++
helpviewer_keywords:
- LINK tool [C++], controlling optimizations
- -OPT linker option
- linker [C++], optimizations
- OPT linker option
- optimization, linker
- /OPT linker option
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86427dbf1ac6c3404daa36d2e02786aa80ed6453
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="opt-optimizations"></a>/OPT (Optimisations)
Contrôle les optimisations effectuées par LINK pendant une génération.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## <a name="arguments"></a>Arguments  
 **REF** &#124; **NOREF**  
 **/ OPT : REF** élimine les fonctions et les données qui ne sont jamais référencées. **/OPT : NOREF** conserve les fonctions et les données qui ne sont jamais référencées.  
  
 Lorsque /OFT:REF est activé, LINK supprime les fonctions et données empaquetées non référencées. Un objet contient des fonctions empaquetées et les données (COMDAT) s’il a été compilé à l’aide de la [/Gy](../../build/reference/gy-enable-function-level-linking.md) option. Cette optimisation porte le nom d'élimination COMDAT transitive. Par défaut, **/OPT : REF** est activé dans les versions non debug. Pour remplacer cette valeur par défaut et conserver les COMDAT dans le programme, spécifiez **/OPT : NOREF**. Vous pouvez utiliser la [/inclure](../../build/reference/include-force-symbol-references.md) option pour substituer la suppression d’un symbole spécifique.  
  
 Lorsque **/OPT : REF** est activé, soit explicitement, soit par défaut, une forme limitée de **/OPT : ICF** est activée afin de replier uniquement des fonctions identiques. Si vous souhaitez **/OPT : REF** mais pas **/OPT : ICF**, vous devez spécifier soit **/OPT : REF, NOICF** ou **NOICF**.  
  
 Si [/DEBUG](../../build/reference/debug-generate-debug-info.md) est spécifié, la valeur par défaut pour **/OPT** est **NOREF**, et toutes les fonctions sont conservées dans l’image. Pour remplacer cette valeur par défaut et optimiser une build de débogage, spécifiez **/OPT : REF**. Étant donné que **/OPT : REF** implique **/OPT : ICF**, nous vous recommandons de spécifier également **NOICF** à conserver des fonctions identiques dans les versions de débogage. Cela facilite la lecture des traces de la pile et la définition des points d’arrêt dans les fonctions qui seraient pliées ensemble dans le cas contraire. Le **/OPT : REF** option désactive les liens incrémentiels.  
  
 Vous devez marquer explicitement `const` les données en tant que COMDAT ; utilisez [__declspec (selectany)](../../cpp/selectany.md).  
  
 Spécification de **/OPT : ICF** n’active pas la **/OPT : REF** option.  
  
 **ICF [=** `iterations` **] &#124; NOICF**   
 Utilisez **/OPT : ICF [=**`iterations`**]** pour effectuer un repli COMDAT identique. Les COMDAT redondants peuvent être supprimés de la sortie de l'éditeur de liens. Le paramètre facultatif `iterations` spécifie la fréquence de recherche des doublons parmi les symboles. Le nombre d'itérations par défaut est de deux. Des itérations supplémentaires peuvent permettre de localiser davantage de doublons n’ayant pas été détectés par pliage au cours de l’itération précédente.  
  
 L’éditeur de liens se comporte différemment lorsque **/OPT : REF** est spécifié, et **ICF** est activée par défaut — que c’est le cas lorsque **/OPT : REF, ICF** est spécifié explicitement. La forme de **ICF** activée avec **/OPT : REF** uniquement ne replie pas les données en lecture seule, cela inclut .rdata, .pdata et .xdata. Par conséquent, moins de fonctions sont repliées lors de la production d'images pour [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], car les fonctions de ces modules dépendent davantage des données en lecture seule, par exemple .pdata et .xdata. Pour obtenir un total **ICF** pliage de comportement, spécifiez explicitement **/OPT : ICF**.  
  
 Pour placer des fonctions dans les COMDAT, vous utilisez la **/Gy** l’option du compilateur ; placer `const` des données, vous devez la déclarer `__declspec(selectany)`. Pour plus d’informations sur la façon de spécifier les données pour le pliage, consultez [selectany](../../cpp/selectany.md).  
  
 Par défaut, **ICF** est activé, si **REF** sur. Pour remplacer cette valeur par défaut si **REF** est spécifié, utilisez **NOICF**. Lorsque **/OPT : REF** n’est pas spécifié dans une version debug, vous devez spécifier explicitement **/OPT : ICF** pour activer le repli COMDAT. Toutefois, étant donné que **/OPT : ICF** peut fusionner des données identiques ou des fonctions, elle peut modifier les noms des fonctions qui apparaissent dans les traces de pile. Elle peut également empêcher la définition de points d'arrêt dans certaines fonctions ou l'examen de certaines données dans le débogueur, et vous amener à des fonctions inattendues lorsque vous effectuez du pas à pas dans le code. Par conséquent, nous ne recommandons pas que vous utilisez **/OPT : ICF** dans les versions debug, sauf si les avantages de taille réduite du code compensent ces inconvénients.  
  
> [!NOTE]
>  Étant donné que **/OPT : ICF** peut entraîner la même adresse à affecter à différentes fonctions ou les membres de données en lecture seule (`const` compilés à l’aide de variables **/Gy**), il peut interrompre un programme qui dépend de adresses uniques pour les fonctions ou les membres de données en lecture seule. Pour plus d’informations, consultez l’article [/Gy (Activer la liaison au niveau des fonctions)](../../build/reference/gy-enable-function-level-linking.md).  
  
 **LBR** &#124; **NOLBR**  
 Le **/OPT : LBR** et **/OPT:NOLBR** options s’appliquent uniquement aux binaires ARM. Étant donné que certaines instructions de branche de processeur ARM ont une plage limitée, si l’éditeur de liens détecte un saut vers une adresse hors limite, il remplace l’adresse de destination de l’instruction de branche par l’adresse d’un « îlot » de code contenant une instruction de branche qui cible la destination réelle. Vous pouvez utiliser **/OPT : LBR** pour optimiser la détection des longues instructions de branche et le positionnement des îlots de code intermédiaires afin de réduire la taille globale du code. **/OPT:NOLBR** fait en sorte que l’éditeur de liens pour générer des îlots de code pour les longues instructions de branche rencontrées, sans optimisation.  
  
 Par défaut, le **/OPT : LBR** option est définie lors de l’édition des liens incrémentielle ne sont pas activé. Si vous souhaitez que des liens non incrémentielle sans optimisations des longues branches, spécifiez **/OPT:NOLBR**. Le **/OPT : LBR** option désactive les liens incrémentiels.  
  
## <a name="remarks"></a>Notes  
 En règle générale, les optimisations diminuent la taille de l'image et augmentent la vitesse du programme. Toutefois, elles entraînent également une augmentation de la durée d'édition des liens.  
  
 Vous pouvez utiliser la [/verbose](../../build/reference/verbose-print-progress-messages.md) option pour afficher les fonctions supprimées par **/OPT : REF** et les fonctions repliées par **/OPT : ICF**.  
  
### <a name="to-set-the-opticf-or-optref-linker-option-in-the-visual-studio-development-environment"></a>Pour définir l'option OPT:ICF ou OPT:REF de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le volet gauche, développez **propriétés de Configuration**, **l’éditeur de liens**, **optimisation**.  
  
3.  Modifiez l'une des propriétés suivantes :  
  
    -   **Activer le repli COMDAT**  
  
    -   **Références**  
  
### <a name="to-set-the-optlbr-linker-option-in-the-visual-studio-development-environment"></a>Pour définir l'option OPT:LBR de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le **l’éditeur de liens** dossier.  
  
3.  Sélectionnez le **ligne de commande** page de propriétés.  
  
4.  Entrez l’option de **des Options supplémentaires**:  
  
     `/opt:lbr`  
  
### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A>.  
  
## <a name="see-also"></a>Voir aussi  
 [Définition des Options de l’éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l’éditeur de liens](../../build/reference/linker-options.md)