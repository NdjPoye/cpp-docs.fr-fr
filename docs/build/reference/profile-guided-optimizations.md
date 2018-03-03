---
title: "Optimisations guidées par profil | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- profile-guided optimizations
- optimization, profile-guided [C++]
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f2d72ddda460a88830f7f7692f4c9707fa3101a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimizations"></a>Optimisations guidées par profil
L'optimisation guidée par profil vous permet d'optimiser un fichier de sortie alors que l'optimiseur utilise les données de séries de tests du fichier .exe ou .dll. Les données représentent la manière dont le programme est susceptible de s'exécuter dans un environnement de production.  
  
 Les optimisations guidées par profil sont uniquement disponibles pour des cibles natives x86 ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]. Les optimisations guidées par profil ne sont pas disponibles pour les fichiers de sortie qui doivent s'exécuter sur le Common Language Runtime. Même si vous produisez un assembly avec du code mixte natif et managé (compilation avec **/CLR**), vous ne pouvez pas utiliser l’optimisation guidée par profil sur le code natif uniquement. Si vous essayez de générer un projet avec ces options dans l'environnement IDE, une erreur de build se produit.  
  
> [!NOTE]
>  Les informations collectées à partir des séries de tests de profilage remplacent les optimisations qui seraient en vigueur si vous spécifiez **/Ob**, **/Os**, ou **/Ot**. Pour plus d’informations, consultez [/Ob (Expansion des fonctions Inline)](../../build/reference/ob-inline-function-expansion.md) et [/Os, /Ot (favoriser la taille du Code, favoriser la vitesse du Code)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md).  
  
 Vous pouvez utiliser l'optimisation guidée par profil automatisée pour le plug-in Visual C++ dans le concentrateur des performances et des diagnostics pour simplifier et rationaliser le processus d'optimisation dans Visual Studio, ou vous pouvez effectuer les étapes d'optimisation manuellement dans Visual Studio ou sur la ligne de commande. Nous recommandons le plug-in car il est plus facile à utiliser. Pour plus d’informations sur la façon d’obtenir le plug-in et l’utiliser pour optimiser votre application, consultez [guidée par profil plug-in optimisation](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
 Le plug-in d'optimisation guidée par profil et l'optimisation manuelle guidée par profil suivent ces étapes pour optimiser votre application :  
  
-   Compilez un ou plusieurs fichiers de code source avec [/GL](../../build/reference/gl-whole-program-optimization.md).  
  
     Chaque module généré avec /GL peut être examiné pendant les séries de tests d'optimisation guidée par profil pour capturer le comportement au moment de l'exécution. Il n'est pas nécessaire que chaque module dans une génération d'optimisation guidée par profil soit compilé avec /GL. Toutefois, seuls les modules compilés avec /GL seront instrumentés et disponibles ultérieurement pour les optimisations guidées par profil.  
  
-   Lier à l’aide de [LTCG](../../build/reference/ltcg-link-time-code-generation.md) et [/genprofile](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md).  
  
     À l’aide de /LTCG et/genprofile crée un fichier .pgd vide. Une fois les données de série de tests ajoutées au fichier .pgd, elles peuvent être utilisées en entrée pour la prochaine étape de liaison (création de l'image optimisée). Lorsque vous spécifiez/genprofile, vous pouvez éventuellement ajouter : PGD =`filename` pour spécifier un autre nom ou emplacement pour le fichier .pgd.  
  
-   Profilez l'application.  
  
     Chaque fois qu’une session EXE profilée se termine ou une DLL profilée est déchargée, un *appname*! # .pgc fichier est créé. Un fichier .pgc contient des informations sur une série de tests d'application particulière. # est un nombre commençant par 1 qui est incrémenté selon le nombre d’autres *appname*! # .pgc des fichiers dans le répertoire. Vous pouvez supprimer un fichier .pgc si la série de tests ne représente pas un scénario que vous souhaitez optimiser.  
  
     Pendant une série de tests, vous pouvez forcer la fermeture du fichier .pgc actuellement ouvert et la création d’un nouveau fichier .pgc avec le [pgosweep](../../build/reference/pgosweep.md) utilitaire (par exemple, lorsque la fin d’un scénario de test ne coïncide pas avec l’arrêt de l’application).  
  
     Vous pouvez utiliser l'option `PogoSafeMode` quand vous profilez votre application. Cette option vous permet de spécifier si vous souhaitez profiler l'application en mode sans échec ou en mode rapide. Pour plus d’informations sur ces modes, consultez [PogoSafeMode](../../build/reference/pogosafemode.md).  
  
-   Lier à l’aide de /LTCG et/useprofile.  
  
     À l’aide de /LTCG et/useprofile crée l’image optimisée. Cette étape accepte en entrée le fichier .pgd. Lorsque vous spécifiez/useprofile, vous pouvez éventuellement ajouter : PGD =`filename` pour spécifier un autre nom ou emplacement pour le fichier .pgd. Pour plus d’informations, consultez [LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Il est même possible de créer le fichier de sortie optimisé et de déterminer ultérieurement qu'un profilage supplémentaire serait utile pour créer une image plus optimisée. Si l'image instrumentée et son fichier .pgd sont disponibles, vous pouvez effectuer des séries de tests supplémentaires et régénérer l'image optimisée avec le fichier .pgd plus récent.  
  
 Vous trouverez ci-dessous une liste des optimisations guidées par profil :  
  
-   **Incorporation (inlining)** , par exemple, s’il existe une fonction A que fréquemment appelle la fonction B et la fonction B est relativement petite, puis les optimisations guidées par profil seront fonction inline B dans la fonction A.  
  
-   **Spéculation sur les appels virtuels** -si un appel virtuel, ou un autre appel via un pointeur fonction, cible fréquemment une certaine fonction, une optimisation guidée par profil peut insérer un appel direct exécuté conditionnellement à la fonction fréquemment ciblée, et l’appel direct peut être inline.  
  
-   **Allocation des registres** - optimisation avec les données de profil entraîne une meilleure allocation des registres.  
  
-   **Optimisation des blocs de base** -optimisation des blocs de base permet des blocs de base fréquemment exécutées qui s’exécutent temporellement dans un frame donné à être placé dans le même jeu de pages (localité). Cela réduit le nombre de pages utilisées, ce qui réduit au maximum la surcharge de la mémoire.  
  
-   **Optimisation de la taille/vitesse** -fonctions auxquelles le programme consacre beaucoup de temps peuvent être optimisées pour la vitesse.  
  
-   **Disposition des fonctions** - basé sur le graphique des appels et profiler le comportement des appelants/appelés, les fonctions qui ont tendance à être sur le même chemin d’exécution sont placées dans la même section.  
  
-   **Optimisation des branches conditionnelles** : en testant les valeurs, guidées par profil optimisations peuvent rechercher si une valeur donnée dans une instruction switch est utilisée plus souvent que d’autres valeurs.  Cette valeur peut ensuite être tirée de l’instruction switch.  La même opération peut être effectuée avec des instructions if/else dans lesquelles l'optimiseur peut organiser les instructions if/else afin que le bloc if ou else soit placé en premier selon le bloc qui est le plus souvent true.  
  
-   **Séparation du Code mort** -Code qui n’est pas appelé pendant le profilage est déplacé vers une section spéciale ajoutée à la fin de l’ensemble des sections. Cela permet de conserver efficacement cette section en dehors des pages utilisées fréquemment.  
  
-   **Séparation du Code EH** -le code EH, en cours d’exécution exceptionnellement, peut souvent être déplacé vers une section distincte lorsque les optimisations guidées par profil peuvent déterminer que les exceptions se produisent uniquement dans des conditions exceptionnelles.  
  
-   **Intrinsèques mémoire** -l’expansion d’éléments intrinsèques peut être conseillée s’il peut être déterminé si un élément intrinsèque est fréquemment appelé. Un élément intrinsèque peut également être optimisé en fonction de la taille de bloc des déplacements ou des copies.  
  
 Pour plus d’informations sur l’exécution d’une optimisation manuelle dans l’IDE ou sur la ligne de commande, consultez [guidée par profil plug-in optimisation](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Plug-in d’optimisation guidée par profil](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [Outils de l’optimisation guidée par profil](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [Guide pratique pour fusionner plusieurs profils PGO en un seul profil](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Outils de génération C/C++](../../build/reference/c-cpp-build-tools.md)