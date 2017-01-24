---
title: "/fp (Sp&#233;cifier le comportement de virgule flottante) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.floatingPointModel"
  - "VC.Project.VCCLWCECompilerTool.FloatingPointExceptions"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.floatingPointModel"
  - "VC.Project.VCCLCompilerTool.FloatingPointExceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/fp (option du compilateur C++)"
  - "-fp (option du compilateur C++)"
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /fp (Sp&#233;cifier le comportement de virgule flottante)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie le comportement de la virgule flottante dans un fichier de code source.  
  
## Syntaxe  
  
```  
/fp:[precise | except[-] | fast | strict ]  
```  
  
## Indicateurs  
 **precise**  
 Valeur par défaut.  
  
 Améliore la cohérence des tests à virgule flottante à des fins d'égalité ou d'inégalité en désactivant les optimisations qui peuvent modifier la précision des calculs à virgule flottante. \(Le maintien d'une précision spécifique est requis pour des raisons de conformité stricte à la norme ANSI.\) Par défaut, dans le code des architectures x86, le compilateur utilise les registres 80 bits du coprocesseur pour stocker les résultats intermédiaires des calculs à virgule flottante.  Cette approche augmente la vitesse du programme tout en diminuant sa taille.  Cependant, dans la mesure où le calcul implique des types de données à virgule flottante qui sont représentés en mémoire sur moins de 80 bits, le fait de faire subir aux bits supplémentaires de précision \(80 bits moins le nombre de bits dans un type à virgule flottante plus petit\) un long calcul peut donner lieu à des résultats incohérents.  
  
 Avec **\/fp:precise** sur des processeurs x86, le compilateur arrondit les variables de type `float` à la précision correcte pour les assignations et les casts, ainsi que lors du passage des paramètres à une fonction.  Cet arrondi permet de garantir que les données ne conserveront pas une importance supérieure à la capacité de leur type.  Un programme compilé avec **\/fp:precise** peut être plus lent et plus volumineux qu'un programme compilé sans **\/fp:precise**.  **\/fp:precise** désactive les intrinsèques. Les routines de la bibliothèque Runtime standard sont utilisées à la place.  Pour plus d'informations, consultez [\/Oi \(Générer des fonctions intrinsèques\)](../../build/reference/oi-generate-intrinsic-functions.md).  
  
 Le comportement suivant en matière de virgule flottante est activé avec **\/fp:precise** :  
  
-   Contractions, à savoir l'utilisation d'une opération composite qui a un seul arrondi à la fin pour remplacer plusieurs opérations.  
  
-   Les optimisations d'expression qui ne sont pas valides pour des valeurs spéciales \(NaN, \+infini, \-infini, \+0, \-0\) ne sont pas autorisées.  Les optimisations x\-x \=\> 0, x\*0 \=\> 0, x\-0 \=\> x, x\+0 \=\> x et 0\-x \=\> \-x ne sont pas valides pour diverses raisons. \(Consultez la documentation relative aux normes IEEE 754 et C99.\)  
  
-   Le compilateur gère correctement les comparaisons qui impliquent NaN.  Par exemple, x \!\= x prend la valeur **true** si `x` est une valeur NaN et si les comparaisons ordonnées qui impliquent NaN lèvent une exception.  
  
-   L'évaluation d'expression respecte FLT\_EVAL\_METHOD\=2 de la norme C99, sauf que lorsque vous programmez pour des processeurs x86, il s'agit d'une précision long double, car le FPU est défini à une précision de 53 bits.  
  
-   La multiplication par 1.0 exactement est transformée en utilisation de l'autre facteur.  x\*y\*1.0 est transformé en x\*y.  De même, x\*1.0\*y est transformé en x\*y.  
  
-   La division par 1.0 exactement est transformée en utilisation du dividende.  x\*y\/1.0 est transformé en x\*y.  De même, x\/1.0\*y est transformé en x\*y.  
  
 L'utilisation de **\/fp:precise** quand [fenv\_access](../../preprocessor/fenv-access.md) a la valeur ON désactive certaines optimisations telles que les évaluations au moment de la compilation des expressions à virgule flottante.  Par exemple, si vous utilisez [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) pour changer le mode d'arrondi et si le compilateur exécute un calcul à virgule flottante, le mode d'arrondi que vous avez spécifié n'est pas appliqué, sauf si `fenv_access` a la valeur ON.  
  
 **\/fp:precise** remplace l'option de compilateur **\/Op**.  
  
 **fast**  
 Crée le code le plus rapide dans la plupart des cas en assouplissant les règles pour l'optimisation des opérations à virgule flottante.  Cela permet au compilateur d'optimiser le code à virgule flottante en matière de vitesse au détriment de la précision.  Lorsque **\/fp:fast** est spécifié, le compilateur risque de ne pas arrondir correctement les instructions d'assignation, les casts de type ou les appels de fonction. En outre, il risque de ne pas effectuer l'arrondi des expressions intermédiaires.  Le compilateur peut réorganiser des opérations ou effectuer des transformations algébriques, par exemple en suivant les règles associatives et distributives, sans tenir compte de leur effet sur la précision finie des résultats.  Le compilateur peut changer les opérations et les opérandes en simple précision au lieu de suivre les règles de promotion de type C\+\+.  Les optimisations des contractions spécifiques à la virgule flottante sont toujours activées \([fp\_contract](../../preprocessor/fp-contract.md) a la valeur ON\).  Les exceptions à virgule flottante et l'accès à l'environnement FPU sont désactivés \(**\/fp:except\-** est implicite et [fenv\_access](../../preprocessor/fenv-access.md) a la valeur OFF\).  
  
 **\/fp:fast** ne peut pas être utilisé avec **\/fp:strict** ou **\/fp:precise**.  La dernière option spécifiée sur la ligne de commande est utilisée.  La spécification de **\/fp:fast** et **\/fp:except** génère une erreur du compilateur.  
  
 La spécification de [\/Za, \/Ze \(Désactiver les extensions de langage\)](../../build/reference/za-ze-disable-language-extensions.md) \(compatibilité ANSI\) et **\/fp:fast** peut entraîner un comportement inattendu.  Par exemple, les opérations à virgule flottante à simple précision ne peuvent pas être arrondies à la simple précision.  
  
 **except\[\-\]**  
 Modèle de virgule flottante fiable.  Les exceptions sont levées aussitôt après leur déclenchement.  Cette option est désactivée par défaut.  L'ajout d'un signe moins à l'option entraîne sa désactivation explicite.  
  
 **strict**  
 Modèle de virgule flottante le plus strict.  **\/fp:strict** oblige [fp\_contract](../../preprocessor/fp-contract.md) à avoir la valeur OFF et [fenv\_access](../../preprocessor/fenv-access.md) à avoir la valeur ON.  **\/fp:except** est implicite et peut être désactivé par la spécification explicite de **\/fp:except\-**.  En cas d'utilisation avec **\/fp:except\-**, **\/fp:strict** applique une sémantique à virgule flottante stricte, mais sans tenir compte des événements exceptionnels.  
  
## Notes  
 Plusieurs options **\/fp** peuvent être spécifiées dans la même compilation.  
  
 Pour contrôler le comportement de la virgule flottante par fonction, consultez le pragma [float\_control](../../preprocessor/float-control.md).  Cela entraîne la substitution du paramètre de compilateur **\/fp**.  Nous vous conseillons d'enregistrer et de restaurer le comportement local en matière de virgule flottante :  
  
```css  
#pragma float_control(precise, on, push)  
// Code that uses /fp:precise mode  
#pragma float_control(pop)  
```  
  
 La plupart des optimisations à virgule flottante liées à **\/fp:strict**, **\/fp:except** \(et aux pragmas correspondants\), ainsi qu'au pragma `fp_contract`, dépendent de l'ordinateur.  **\/fp:strict** et **\/fp:except** ne sont pas compatibles avec **\/clr**.  
  
 **\/fp:precise** doit répondre à la plupart des exigences d'une application en matière de virgule flottante.  Vous pouvez utiliser **\/fp:except** et **\/fp:strict**, mais cela peut entraîner une baisse des performances.  Si les performances sont une priorité, songez à utiliser **\/fp:fast**.  
  
 **\/fp:strict**, **\/fp:fast** et **\/fp:precise** sont des modes de précision \(exactitude\).  Une seule de ces options peut être active à la fois.  Si **\/fp:strict** et **\/fp:precise** sont spécifiés, le compilateur utilise celui qu'il traite en dernier.  **\/fp:strict** et **\/fp:fast** ne peuvent pas être spécifiés.  
  
 Pour plus d'informations, consultez [Optimisation du code en virgule flottante avec Microsoft Visual C\+\+](http://msdn.microsoft.com/library/aa289157.aspx).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **C\/C\+\+**.  
  
4.  Sélectionnez la page de propriétés **Génération de code**.  
  
5.  Modifiez la propriété **Modèle de virgule flottante**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Optimisation du code en virgule flottante avec Microsoft Visual C\+\+](http://msdn.microsoft.com/library/aa289157.aspx)