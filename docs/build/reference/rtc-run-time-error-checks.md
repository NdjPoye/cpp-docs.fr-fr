---
title: "/RTC (V&#233;rifications des erreurs au moment de l&#39;ex&#233;cution) | Microsoft Docs"
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
  - "/rtc"
  - "VC.Project.VCCLCompilerTool.SmallerTypeCheck"
  - "VC.Project.VCCLCompilerTool.UninitializedVariableCheck"
  - "VC.Project.VCCLCompilerTool.StackFrameCheck"
  - "VC.Project.VCCLCompilerTool.BasicRuntimeChecks"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RTC1 (option du compilateur C++)"
  - "/RTCc (option du compilateur C++)"
  - "/RTCs (option du compilateur C++)"
  - "/RTCu (option du compilateur C++)"
  - "__MSVC_RUNTIME_CHECKS (macro)"
  - "RTC1 (option du compilateur)"
  - "-RTC1 (option du compilateur C++)"
  - "RTCc (option du compilateur)"
  - "-RTCc (option du compilateur C++)"
  - "RTCs (option du compilateur)"
  - "-RTCs (option du compilateur C++)"
  - "RTCu (option du compilateur)"
  - "-RTCu (option du compilateur C++)"
  - "vérifications à l'exécution, /RTC (option)"
  - "erreurs d'exécution, vérification des erreurs"
  - "erreurs d'exécution, vérifications à l'exécution"
ms.assetid: 9702c558-412c-4004-acd5-80761f589368
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /RTC (V&#233;rifications des erreurs au moment de l&#39;ex&#233;cution)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Permet d'activer et de désactiver la fonctionnalité de vérification des erreurs au moment de l'exécution, conjointement avec le pragma [runtime\_checks](../../preprocessor/runtime-checks.md).  
  
## Syntaxe  
  
```  
/RTC1  
/RTCc  
/RTCs  
/RTCu  
```  
  
## Arguments  
 `1`  
 Équivalent de **\/RTC**`su`.  
  
 `c`  
 Signale quand une valeur est assignée à un type de données plus petit qui se traduit par une perte de données.  Par exemple, si vous avez assigné une valeur de type `short 0x101` à une variable de type `char`.  
  
 Cette option signale les situations où vous avez l'intention de tronquer, par exemple quand vous voulez que les huit premiers bits d'un `int` soient retournés en tant que `char`.  Comme **\/RTC**`c` génère une erreur au moment de l'exécution si des informations risquent d'être perdues à la suite de l'assignation, vous pouvez masquer les informations dont vous avez besoin pour éviter une erreur au moment de l'exécution en raison de **\/RTC**`c`.  Par exemple :  
  
```  
#include <crtdbg.h>  
  
char get8bits(int value, int position) {  
   _ASSERT(position < 32);  
   return (char)(value >> position);  
   // Try the following line instead:  
   // return (char)((value >> position) & 0xff);  
}  
  
int main() {  
   get8bits(12341235,3);  
}  
```  
  
 `s`  
 Active les vérifications des erreurs au moment de l'exécution pour le frame de pile, comme suit :  
  
-   Initialisation de variables locales à une valeur différente de zéro.  Cela permet d'identifier les bogues qui n'apparaissent pas lors d'une exécution en mode débogage.  Les chances sont plus grandes de voir les variables de la pile rester à zéro dans une version Debug par rapport à une version Release en raison des optimisations qu'applique le compilateur aux variables de la pile dans cette dernière.  Une fois que le programme a utilisé une zone de sa pile, il n'est jamais remis à 0 par le compilateur.  Par conséquent, les variables de pile suivantes non initialisées qui utilisent par hasard la même zone de pile peuvent retourner les valeurs datant de l'utilisation précédente de la mémoire de cette pile.  
  
-   Détection de dépassements et sous\-exécutions de variables locales telles que les tableaux.  **\/RTC**`s` ne détecte pas de débordements lors de l'accès à la mémoire qui est le résultat du remplissage du compilateur dans une structure.  Le remplissage peut se produire à la suite de l'utilisation de [align](../../cpp/align-cpp.md), [\/Zp \(Alignement des membres de la structure\)](../../build/reference/zp-struct-member-alignment.md) ou [pack](../../preprocessor/pack.md), ou si vous ordonnez les éléments de la structure d'une façon qui impose au compilateur d'exécuter un remplissage.  
  
-   Vérification du pointeur de pile, qui détecte l'altération des pointeurs de pile.  L'altération des pointeurs de pile peut être due à une discordance de convention d'appel.  Par exemple, vous utilisez un pointeur fonction pour appeler une fonction dans une DLL qui est exportée en tant que [\_\_stdcall](../../cpp/stdcall.md), mais vous déclarez le pointeur désignant la fonction en tant que [\_\_cdecl](../../cpp/cdecl.md).  
  
 `u`  
 Signale les variables qui sont utilisées sans avoir été initialisées.  Par exemple, une instruction qui génère `C4701` peut également générer une erreur au moment de l'exécution sous **\/RTC**`u`.  Toute instruction qui génère [Avertissement du compilateur \(niveaux 1 et 4\) C4700](../../error-messages/compiler-warnings/compiler-warning-level-1-and-level-4-c4700.md) générera également une erreur au moment de l'exécution sous **\/RTC**`u`.  
  
 Cependant, considérons le fragment de code suivant :  
  
```  
int a, *b, c;  
if ( 1 )  
b = &a;  
c = a;  // No run-time error with /RTCu  
```  
  
 Si une variable aurait pu être initialisée, elle n'est pas signalée au moment de l'exécution par **\/RTC**`u`.  Par exemple, après l'utilisation d'un alias via un pointeur pour une variable, le compilateur ne suit pas la variable et n'indique pas des emplois non initialisés.  En fait, vous pouvez initialiser une variable en acceptant son adresse.  L'opérateur & fonctionne comme un opérateur d'assignation dans ce cas.  
  
## Notes  
 Les vérifications des erreurs au moment de l'exécution sont un moyen de rechercher les problèmes dans votre code en cours ; pour plus d'informations, consultez [Comment : utiliser les contrôles natifs à l'exécution](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
 Si vous compilez votre programme sur la ligne de commande en utilisant l'une des options du compilateur **\/RTC**, les instructions du pragma [optimize](../../preprocessor/optimize.md) figurant dans votre code échoueront silencieusement.  La raison en est que les vérifications des erreurs au moment de l'exécution ne sont pas valides dans une version Release \(optimisée\).  
  
 Vous devez utiliser **\/RTC** pour les builds de développement ; **\/RTC** ne doit pas être employé pour une version commerciale.  **\/RTC** ne peut pas être utilisé avec les optimisations du compilateur \([\/O \(Optimiser le code\), options](../../build/reference/o-options-optimize-code.md)\).  Une image de programme générée avec **\/RTC** sera légèrement plus grande et plus lente qu'une image générée avec **\/Od** \(jusqu'à 5 pour cent plus lente qu'une génération **\/Od**\).  
  
 La directive du préprocesseur \_\_MSVC\_RUNTIME\_CHECKS sera définie lorsque vous utiliserez une option **\/RTC** ou [\/GZ](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **C\/C\+\+**.  
  
3.  Cliquez sur la page de propriétés **Génération de code**.  
  
4.  Modifiez l'une des deux propriétés suivantes : **Vérifications de base à l'exécution** ou **Vérification des types les plus petits**, ou les deux.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez les propriétés <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BasicRuntimeChecks%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SmallerTypeCheck%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [RTC sample](http://msdn.microsoft.com/fr-fr/b3415b09-f6fd-43dc-8c02-9a910bc2574e)