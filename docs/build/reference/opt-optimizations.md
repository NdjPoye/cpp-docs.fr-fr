---
title: "/OPT (Optimisations) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.OptimizeReferences"
  - "/opt"
  - "VC.Project.VCLinkerTool.OptimizeForWindows98"
  - "VC.Project.VCLinkerTool.EnableCOMDATFolding"
  - "VC.Project.VCLinkerTool.OptimizeFolding"
  - "VC.Project.VCLinkerTool.FoldingIterations"
  - "VC.Project.VCLinkerTool.OptimizeFoldingIterations"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/OPT (option de l'éditeur de liens)"
  - "LINK (outil C++), contrôler les optimisations"
  - "éditeur de liens (C++), optimisations"
  - "OPT (option de l'éditeur de liens)"
  - "-OPT (option de l'éditeur de liens)"
  - "optimisation, éditeur de liens"
ms.assetid: 8f229863-5f53-48a8-9478-243a647093ac
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# /OPT (Optimisations)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle les optimisations effectuées par LINK pendant une génération.  
  
## Syntaxe  
  
```  
/OPT:{REF | NOREF}  
/OPT:{ICF[=iterations] | NOICF}  
/OPT:{LBR | NOLBR}  
```  
  
## Arguments  
 **REF** &#124; **NOREF**  
 **\/OPT:REF** élimine les fonctions et les données qui ne sont jamais référencées. **\/OPT:NOREF** conserve les fonctions et les données qui ne sont jamais référencées.  
  
 Lorsque \/OFT:REF est activé, LINK supprime les fonctions et données empaquetées non référencées.  Un objet contient des fonctions et données empaquetées \(COMDAT\) s'il a été compilé à l'aide de l'option [\/Gy](../../build/reference/gy-enable-function-level-linking.md).  Cette optimisation porte le nom d'élimination COMDAT transitive.  Par défaut, **\/OPT:REF** est activé dans les versions non Debug.  Pour substituer cette valeur par défaut et conserver les COMDAT non référencés dans le programme, spécifiez **\/OPT:NOREF**.  Vous pouvez utiliser l'option [\/INCLUDE](../../build/reference/include-force-symbol-references.md) pour substituer la suppression d'un symbole spécifique.  
  
 Lorsque **\/OPT:REF** est activé, soit explicitement, soit par défaut, une forme limitée de **\/OPT:ICF** est activée afin de replier uniquement les fonctions identiques.  Si vous voulez **\/OPT:REF** mais pas **\/OPT:ICF**, vous devez spécifier **\/OPT:REF,NOICF** ou **\/OPT:NOICF**.  
  
 Si [\/DEBUG](../../build/reference/debug-generate-debug-info.md) est spécifié, la valeur par défaut de **\/OPT** est **NOREF**, et toutes les fonctions sont conservées dans l'image.  Pour substituer cette valeur par défaut et optimiser une build de débogage, spécifiez **\/OPT:REF**.  Comme **\/OPT:REF** implique **\/OPT:ICF**, nous vous recommandons de spécifier également **\/OPT:NOICF** pour conserver des fonctions identiques dans les builds de débogage.  Cela facilite la lecture des traces de la pile et la définition des points d'arrêt dans les fonctions qui seraient repliées ensemble dans le cas contraire.  L'option **\/OPT:REF** désactive l'édition des liens incrémentielle.  
  
 Vous devez marquer explicitement les données `const` en tant que COMDAT à l'aide de [\_\_declspec\(selectany\)](../../cpp/selectany.md).  
  
 La spécification de **\/OPT:ICF** n'active pas l'option **\/OPT:REF**.  
  
 **ICF\[\=**  `iterations` **\] &#124; NOICF**  
 Utilisez **\/OPT:ICF\[\=**`iterations`**\]** pour effectuer un repli COMDAT identique.  Les COMDAT redondants peuvent être supprimés de la sortie de l'éditeur de liens.  Le paramètre facultatif `iterations` spécifie la fréquence de recherche des doublons parmi les symboles.  Le nombre d'itérations par défaut est de deux.  Des itérations supplémentaires peuvent permettre de localiser davantage de doublons n'ayant pas été détectés par repli au cours de l'itération précédente.  
  
 L'éditeur de liens ne se comporte pas de la même façon lorsque **\/OPT:REF** est spécifié \(**ICF** est activé par défaut\) et lorsque **\/OPT:REF,ICF** est spécifié explicitement.  La forme de **ICF** activée avec **\/OPT:REF** uniquement ne replie pas les données en lecture seule \(cela inclut .rdata, .pdata et .xdata\).  Par conséquent, moins de fonctions sont repliées lors de la production d'images pour [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], car les fonctions de ces modules dépendent davantage des données en lecture seule, par exemple .pdata et .xdata.  Pour obtenir un comportement de repli **ICF** complet, spécifiez explicitement **\/OPT:ICF**.  
  
 Pour placer des fonctions dans des COMDAT, utilisez l'option de compilateur **\/Gy**. Pour placer des données `const`, déclarez\-les avec `__declspec(selectany)`.  Pour plus d'informations sur la spécification des données pour le repli, consultez [selectany](../../cpp/selectany.md).  
  
 Par défaut, **ICF** est activé, si **REF** est activé.  Pour remplacer cette valeur par défaut si **REF** est spécifié, utilisez **NOICF**.  Lorsque **\/OPT:REF** n'est pas spécifié dans une version Debug, vous devez spécifier explicitement **\/OPT:ICF** pour activer le repli COMDAT.  Toutefois, comme l'option **\/OPT:ICF** peut fusionner des données ou des fonctions identiques, elle peut modifier les noms des fonctions qui apparaissent dans les traces de la pile.  Elle peut également empêcher la définition de points d'arrêt dans certaines fonctions ou l'examen de certaines données dans le débogueur, et vous amener à des fonctions inattendues lorsque vous effectuez du pas à pas dans le code.  Par conséquent, nous vous déconseillons d'utiliser **\/OPT:ICF** dans les versions Debug à moins que les avantages liés à une taille réduite du code compensent ces inconvénients.  
  
> [!NOTE]
>  Dans la mesure où **\/OPT:ICF** peut entraîner l'assignation de la même adresse à des fonctions distinctes ou à des membres de données en lecture seule \(variables `const` compilées à l'aide de **\/Gy**\), cela peut interrompre l'exécution d'un programme qui dépend d'adresses uniques pour les fonctions ou les membres de données en lecture seule.  Pour plus d'informations, consultez [\/Gy \(Activer la liaison au niveau des fonctions\)](../../build/reference/gy-enable-function-level-linking.md).  
  
 **LBR** &#124; **NOLBR**  
 Les options **\/OPT:LBR** et **\/OPT:NOLBR** s'appliquent uniquement aux binaires ARM.  Étant donné que certaines instructions de branche de processeur ARM ont une plage limitée, si l'éditeur de liens détecte un saut vers une adresse hors limite, il remplace l'adresse de destination de l'instruction de branche par l'adresse d'un « îlot » de code contenant une instruction de branche qui cible la destination réelle.  Vous pouvez utiliser **\/OPT:LBR** pour optimiser la détection des longues instructions de branche et le positionnement des îlots de code intermédiaires afin de réduire la taille globale du code.  **\/OPT:NOLBR** indique à l'éditeur de liens de générer des îlots de code pour les longues instructions de branche rencontrées, sans optimisation.  
  
 Par défaut, l'option **\/OPT:LBR** est définie lorsque l'édition des liens incrémentielle n'est pas activée.  Si vous souhaitez une édition des liens non incrémentielle sans optimisations des longues branches, spécifiez **\/OPT:NOLBR**.  L'option **\/OPT:LBR** désactive l'édition des liens incrémentielle.  
  
## Notes  
 En règle générale, les optimisations diminuent la taille de l'image et augmentent la vitesse du programme. Toutefois, elles entraînent également une augmentation de la durée d'édition des liens.  
  
 Vous pouvez utiliser l'option [\/VERBOSE](../../build/reference/verbose-print-progress-messages.md) pour afficher les fonctions supprimées par **\/OPT:REF** et les fonctions repliées par **\/OPT:ICF**.  
  
### Pour définir l'option OPT:ICF ou OPT:REF de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le volet gauche, développez **Propriétés de configuration**, **Éditeur de liens**, **Optimisation**.  
  
3.  Modifiez l'une des propriétés suivantes :  
  
    -   **Activer le repli COMDAT**  
  
    -   **Références**  
  
### Pour définir l'option OPT:LBR de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Entrez l'option dans **Options supplémentaires** :  
  
     `/opt:lbr`  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableCOMDATFolding%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OptimizeReferences%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)