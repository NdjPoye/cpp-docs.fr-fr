---
title: / GENPROFILE, /FASTGENPROFILE (générer la Build instrumentée de profilage) | Documents Microsoft
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7961ff46661b8f6df2768591932699c3965d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE, /FASTGENPROFILE (Générer une build instrumentée de profilage)

Spécifie la génération d’un fichier .pgd par l’éditeur de liens pour prendre en charge l’optimisation guidée par profil. **/ GENPROFILE** et **/fastgenprofile** utiliser les paramètres par défaut différents. Utilisez **/genprofile** à privilégier la précision d’utilisation de vitesse et de la mémoire pendant le profilage. Utilisez **/fastgenprofile** pour favoriser une utilisation plus petite de la mémoire et la vitesse sur la précision.

## <a name="syntax"></a>Syntaxe

> **/ GENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **EXACT**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Chemin d’accès**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_nom de fichier_}]<br/>
> **/ FASTGENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **EXACT**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Chemin d’accès**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_nom de fichier_}]

### <a name="arguments"></a>Arguments

Un des arguments suivants peut être spécifié pour **/genprofile** ou **/fastgenprofile**. Les arguments répertoriés ici séparés par une barre verticale (**|**) caractère s’excluent mutuellement. Utilisez une virgule (**,**) caractère pour séparer les options.

**COUNTER32** &AMP;#124; **COUNTER64**<br/>
Utilisez **COUNTER32** pour spécifier l’utilisation des compteurs de sonde 32 bits, et **COUNTER64** pour spécifier des compteurs de sonde 64 bits. Lorsque vous spécifiez **/genprofile**, la valeur par défaut est **COUNTER64**. Lorsque vous spécifiez **/FASTGENPROFILE**, la valeur par défaut est **COUNTER32**.

**EXACT** &AMP;#124; **NOEXACT**<br/>
Utilisez **EXACT** pour spécifier des incréments à blocage de thread-safe pour les sondes. **NOEXACT** spécifie les opérations d’incrément non protégées pour les sondes. La valeur par défaut est **NOEXACT**.

**MEMMAX**=*valeur*, **MEMMIN**=*valeur*<br/>
Utilisez **MEMMAX** et **MEMMIN** pour spécifier les tailles de réservation maximale et minimale pour les données d’apprentissage en mémoire. La valeur est la quantité de mémoire à réserver en octets. Par défaut, ces valeurs sont déterminées par une méthode heuristique interne.

**CHEMIN D’ACCÈS** &AMP;#124; **NOPATH**  <br/>
Utilisez **chemin d’accès** pour spécifier un ensemble distinct de compteurs PGO pour chaque chemin unique vers une fonction. Utilisez **NOPATH** pour ne spécifier qu’un ensemble de compteurs pour chaque fonction. Lorsque vous spécifiez **/genprofile**, la valeur par défaut est **chemin d’accès** . Lorsque vous spécifiez **/FASTGENPROFILE**, la valeur par défaut est **NOPATH** .

**TRACKEH** &AMP;#124; **NOTRACKEH**  <br/>
Spécifie s’il faut utiliser des compteurs supplémentaires pour conserver un décompte précis quand des exceptions sont levées au cours de l’apprentissage. Utilisez **TRACKEH** pour spécifier des compteurs supplémentaires pour un nombre exact. Utilisez **NOTRACKEH** pour spécifier des compteurs uniques pour le code qui n’utilise pas d’exception manipulation ou qui ne rencontrent pas d’exceptions dans vos scénarios de formation.  Lorsque vous spécifiez **/genprofile**, la valeur par défaut est **TRACKEH** . Lorsque vous spécifiez **/FASTGENPROFILE**, la valeur par défaut est **NOTRACKEH** .

**PGD**=*nom de fichier*<br/>
Spécifie un nom de fichier de base pour le fichier .pgd. Par défaut, l’éditeur de liens utilise le nom du fichier image exécutable de base avec une extension .pgd.

## <a name="remarks"></a>Notes

Le **/genprofile** et **/fastgenprofile** options indiquent à l’éditeur de liens pour générer le fichier d’instrumentation profilage nécessaire pour prendre en charge de la formation de l’application pour l’optimisation guidée par profil (PGO). Ces options sont nouvelles dans Visual Studio 2015. Préférez ces options à la fonctionnalité déconseillée **/LTCG : PGINSTRUMENT**, **/PGD** et **/POGOSAFEMODE** options et **PogoSafeMode**,  **VCPROFILE_ALLOC_SCALE** et **VCPROFILE_PATH** variables d’environnement. Les informations de profilage générées par l’apprentissage de l’application sont utilisées comme entrée pour effectuer les optimisations de la totalité du programme ciblé pendant les générations. Vous pouvez définir des options supplémentaires pour contrôler différentes fonctionnalités de profilage pour les performances pendant l’apprentissage de l’application et les builds. Les options par défaut spécifiées par **/genprofile** donner des résultats plus précis, en particulier pour les applications multithreads volumineuses et complexes. Le **/fastgenprofile** option utilise les valeurs par défaut différentes pour un encombrement mémoire moindre et les meilleures performances lors de la formation, au détriment de la précision.

Informations de profilage sont capturées lorsque vous exécutez l’application instrumentée après avoir généré à l’aide de **/genprofile** de **/fastgenprofile**. Ces informations sont capturées lorsque vous spécifiez la [/useprofile](useprofile.md) option de l’éditeur de liens pour effectuer le profilage de l’étape et puis utilisé afin de guider l’étape de génération optimisée. Pour plus d’informations sur la façon d’effectuer l’apprentissage de votre application et des détails sur les données collectées, consultez [optimisation guidée par profil](profile-guided-optimizations.md).

Vous devez également spécifier **LTCG** lorsque vous spécifiez **/genprofile** ou **/fastgenprofile**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../../ide/working-with-project-properties.md).

1. Sélectionnez le **propriétés de Configuration** > **l’éditeur de liens** > **ligne de commande** page de propriétés.

1. Entrez le **/genprofile** ou **/FASTGENPROFILE** options et les arguments dans le **des Options supplémentaires** boîte. Choisissez **OK** pour enregistrer vos modifications.

### <a name="to-set-this-linker-option-programmatically"></a>Pour définir cette option de l'éditeur de liens par programmation

- Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Voir aussi

[Définition des options de l’Éditeur de liens](../../build/reference/setting-linker-options.md)<br/>
[Options de l’éditeur de liens](../../build/reference/linker-options.md)<br/>
[/LTCG (Génération de code durant l’édition de liens)](../../build/reference/ltcg-link-time-code-generation.md)<br/>
