---
title: "/kernel (Cr&#233;er un fichier binaire pour le mode noyau) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/kernel"
  - "/kernel-"
dev_langs: 
  - "C++"
ms.assetid: 6d7fdff0-c3d1-4b78-9367-4da588ce8b05
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /kernel (Cr&#233;er un fichier binaire pour le mode noyau)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un binaire qui peut être exécuté sur le noyau windows.  
  
## Syntaxe  
  
```  
/kernel[-]  
```  
  
## Arguments  
 **\/kernel**  
 Le code du projet en cours est compilé et lié à l'aide d'un ensemble de règles du langage C\+\+ qui sont spécifiques à du code qui s'exécute en mode noyau.  
  
 **\/kernel\-**  
 Le code du projet en cours est compilé et lié sans utiliser les règles du langage C\+\+ qui sont spécifiques à du code qui s'exécute en mode noyau.  
  
## Notes  
 Il n'existe aucun `#pragma` équivalent pour contrôler cette option.  
  
 Spécifier l'option de **\/kernel** demande au compilateur et à l'éditeur de liens d'arbitrer quelles fonctionnalités du langage sont autorisées dans le mode noyau et de vérifier que vous avez une puissance d'expression suffisante pour éviter une instabilité d'exécution qui est spécifique au mode noyau C\+\+.  Cela est possible en interdisant l'utilisation des fonctionnalités du langage C\+\+ qui sont disruptives en mode noyau et en fournissant des avertissements pour les fonctionnalités du langage C\+\+ qui sont potentiellement disruptives mais ne peuvent pas être désactivées.  
  
 L'option de **\/kernel** s'applique à la fois aux étapes du compilateur et de l'éditeur de liens d'une génération et est définie au niveau du projet.  Passez le sélecteur de **\/kernel** pour indiquer au compilateur que le binaire résultant, après avoir été lié, doit être chargé dans le noyau Windows.  Le compilateur limitera l'éventail des fonctionnalités du langage C\+\+ à un sous\-ensemble compatible avec le noyau.  
  
 Le tableau suivant répertorie les modifications de comportement du compilateur lorsque **\/kernel** est spécifié.  
  
|Type de comportement|comportement de **\/kernel**|  
|--------------------------|----------------------------------|  
|Gestion d'exceptions C\+\+|Désactivé.  Les instances des mots clés `throw` et `try` émettent une erreur du compilateur \(excepté pour la spécification d'exception `throw()`\).  Aucune option **\/EH** n'est compatible avec **\/kernel**, à l'exception de **\/EH\-**.|  
|RTTI|Désactivé.  Les instances des mots clés `dynamic_cast` et `typeid` émettent une erreur du compilateur, sauf si `dynamic_cast` est utilisé de manière statique.|  
|`new` et `delete`|Vous devez définir explicitement l'opérateur `new()` ou `delete()` ; ni le compilateur ni le runtime ne fournit une définition par défaut.|  
  
 Les conventions d'appel personnalisées, l'option de génération de [\/GS](../../build/reference/gs-buffer-security-check.md), et toutes les optimisations sont autorisées lorsque vous utilisez l'option **\/kernel**.  L'inclusion n'est pas quasiment pas affectée par **\/kernel**, avec la même sémantique respectée par le compilateur.  Si vous souhaitez vous assurer que le qualificateur `__forceinline` inclu est respecté, vous devez vous assurer que l'avertissement [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) est activé afin que vous sachiez lorsqu'une fonction `__forceinline` spécifique n'est pas incluse.  
  
 Lorsque le compilateur se voit passé le sélecteur **\/kernel**, il prédéfinit une macro du préprocesseur nommée `_KERNEL_MODE` et détient la valeur **1**.  Vous pouvez l'utiliser pour compiler du code de manière conditionnelle selon que l'environnement d'exécution est en mode utilisateur ou en mode noyau.  Par exemple, le code suivant spécifie que la classe doit figurer dans un segment non paginable de mémoire lorsqu'elle est compilée pour une exécution en mode noyau.  
  
```cpp  
#ifdef _KERNEL_MODE  
#define NONPAGESECTION __declspec(code_seg("$kerneltext$"))  
#else  
#define NONPAGESECTION  
#endif  
  
class NONPAGESECTION MyNonPagedClass  
{  
  
};  
  
```  
  
 Certaines combinaisons suivantes de l'architecture cible et l'option **\/arch** génèrent une erreur lorsqu'ils sont utilisés avec **\/kernel**:  
  
-   **\/arch:{SSE&#124;SSE2&#124;AVX}** ne sont pas pris en charge sur x86.  Seuls **\/arch:IA32** est pris en charge avec **\/kernel** sur x86.  
  
-   **\/arch:AVX** n'est pas pris en charge avec **\/kernel** sur x64.  
  
 Génération avec **\/kernel** passe également **\/kernel** à l'éditeur de liens.  Voici comment cela affecte le comportement de l'éditeur de liens :  
  
-   La liaison incrémentielle est désactivée.  Si vous ajoutez **\/incremental** sur la ligne de commande, l'éditeur de liens émet cette erreur irrécupérable :  
  
     **LINK : fatal error LNK1295: '\/INCREMENTAL' not compatible with '\/KERNEL' specification; link without '\/INCREMENTAL'**  
  
-   L'éditeur de liens inspecte chaque fichier objet \(ou tout membre des archive inclu depuis les bibliothèques statiques\) pour voir s'il aurait pu être compilé à l'aide de l'option **\/kernel** mais ne l'a pas été.  Si les instances répondent à ce critère, l'éditeur de liens met toujours en place les liens correctement mais peut publier un avertissement, comme indiqué dans le tableau suivant.  
  
    ||**\/kernel** obj|obj de **\/kernel\-**, obj de MASM, ou cvtresed|Combinaison de **\/kernel** et des objs de **\/kernel\-**|  
    |-|----------------------|-----------------------------------------------------|---------------------------------------------------------------|  
    |**lien \/kernel**|Oui|Oui|Oui avec un avertissement LNK4257|  
    |**link**|Oui|Oui|Oui|  
  
     **LNK4257 linking object not compiled with \/KERNEL ; image may not run**  
  
 L'option de **\/kernel** et l'option de **\/driver** s'exécutent indépendamment et n'ont aucune incidence l'un sur l'autre.  
  
### Pour définir l'option \/kernel de compilateur dans Visual Studio.  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Dans la zone **Options supplémentaires**, ajoutez `/kernel` ou `/kernel-`.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)