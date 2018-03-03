---
title: Les Options de NMAKE | Documents Microsoft
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
- NMAKE program, options
ms.assetid: 00ba1aec-ef27-44cf-8d82-c5c095e45bae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef3b987de737d8300f88690754456b73c946180
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-options"></a>Options de NMAKE
Options de NMAKE sont décrites dans le tableau suivant. Options sont précédées par une barre oblique (/) ou d’un tiret (-) et ne sont pas respecter la casse. Utilisez [! CMDSWITCHES](../build/makefile-preprocessing-directives.md) pour modifier les paramètres d’option dans un makefile ou Tools.ini.  
  
|Option|Objectif|  
|------------|-------------|  
|/A|Force la génération de toutes les cibles évaluées, même s’il y a pas obsolète en ce qui concerne les objets dépendants. Ne force pas la génération de cibles non liées.|  
|/B|Force la génération même si les horodateurs sont égales. Recommandé uniquement pour les systèmes très rapides (résolution de deux secondes ou moins).|  
|/C|Supprime la sortie par défaut, y compris le message de copyright de NMAKE ou les avertissements, les horodateurs et les erreurs NMAKE récupérables. Supprime les avertissements émis par l’option /K.|  
|/D|Affiche les horodatages de chaque évaluée cible et dépendant et un message lorsqu’une cible n’existe pas. Utile avec /P pour le débogage d’un makefile. Utilisez **! CMDSWITCHES** pour définir ou supprimer l’option /D pour une partie d’un makefile.|  
|/E|Les causes les variables d’environnement substituent les définitions de macro makefile.|  
|/ ERRORREPORT [NONE &#124; INVITE DE COMMANDES &#124; FILE D’ATTENTE &#124; ENVOI]|Si nmake.exe échoue lors de l’exécution, vous pouvez utiliser /ERRORREPORT pour envoyer des informations à Microsoft à propos de ces erreurs internes.<br /><br /> Pour plus d’informations sur/errorreport, consultez [/errorReport (signaler les erreurs du compilateur interne)](../build/reference/errorreport-report-internal-compiler-errors.md).|  
|/F`filename`|Spécifie `filename` en tant que makefile. Des espaces ou des tabulations peuvent précéder `filename`. Spécifiez l’option /F une fois pour chaque makefile. Pour fournir un makefile à partir de l’entrée standard, spécifiez un tiret (-) pour `filename`et de fin d’entrée au clavier par F6 ou CTRL + Z.|  
|/G|Affiche les makefiles inclus avec le ! INCLUDE (directive).  Consultez [Directives de prétraitement Makefile](../build/makefile-preprocessing-directives.md) pour plus d’informations.|  
|/HELP, / ?|Affiche un bref résumé de syntaxe de ligne de commande NMAKE.|  
|/I|Ignore les codes de sortie à partir de toutes les commandes. Pour définir ou supprimer l’option /I pour une partie d’un makefile, utilisez **! CMDSWITCHES**. Pour ignorer les codes de sortie pour une partie d’un makefile, utilisez un modificateur de commande tiret (-) ou [. Ignorer](../build/dot-directives.md). Substitue /K si les deux sont spécifiées.|  
|/K|Poursuit la génération des dépendances non liées, si une commande retourne une erreur. Également émet un avertissement et retourne un code de sortie 1. Par défaut, NMAKE s’arrête si une commande retourne un code de sortie différent de zéro. Avertissements de /K sont supprimés par /C ; /I substitue /K si les deux sont spécifiées.|  
|/N|Affiche, mais ne pas exécuter de commandes ; les commandes de prétraitement sont exécutées. N’affiche pas les commandes dans les appels récursifs de NMAKE. Utile pour le débogage de makefiles et le contrôle des horodatages. Pour définir ou supprimer l’option /N pour une partie d’un makefile, utilisez **! CMDSWITCHES**.|  
|/NOLOGO|Supprime le message de copyright de NMAKE.|  
|/P|Affiche des informations (définitions de macros, règles d’inférence, cibles, [. SUFFIXES](../build/dot-directives.md) liste) vers une sortie standard, puis exécute la génération. Si aucun makefile ou une cible de ligne de commande n’existe, il affiche des informations uniquement. Utilisez avec /D pour déboguer un makefile.|  
|/Q|Vérifie les horodatages des cibles ; n’exécute pas la génération. Retourne un code de sortie zéro si toutes les cibles sont à jour et un code de sortie différent de zéro si toute cible n’est pas. Les commandes de prétraitement sont exécutées. Utile lors de l’exécution de NMAKE à partir d’un fichier de commandes.|  
|/R|Efface le **. SUFFIXES** liste et ignore les règles d’inférence et les macros qui sont définies dans le fichier Tools.ini ou qui sont prédéfinis.|  
|/S|Supprime l’affichage des commandes exécutées. Pour supprimer l’affichage dans une partie d’un makefile, utilisez le  **@**  modificateur de commande ou [. En mode silencieux](../build/dot-directives.md). Pour définir ou supprimer l’option /S pour une partie d’un makefile, utilisez **! CMDSWITCHES**.|  
|/T|Met à jour les horodatages des cibles de ligne de commande (ou la première cible du makefile) et exécute les commandes de prétraitement mais n’exécute pas la génération.|  
|/U|Doit être utilisé en conjonction avec /N. Fait un dump des fichiers NMAKE inline afin que la sortie /N peut être utilisée comme un fichier de commandes.|  
|/X`filename`|Envoie la sortie d’erreur NMAKE à `filename` au lieu de l’erreur standard. Des espaces ou des tabulations peuvent précéder `filename`. Pour envoyer la sortie d’erreur vers une sortie standard, spécifiez un tiret (-) pour `filename`. N’affecte pas la sortie des commandes vers l’erreur standard.|  
|/Y|Désactive les règles d’inférence en mode batch. Lorsque cette option est sélectionnée, toutes les règles d’inférence en mode batch sont traitées comme des règles d’inférence ordinaires.|  
  
## <a name="see-also"></a>Voir aussi  
 [Exécution de NMAKE](../build/running-nmake.md)