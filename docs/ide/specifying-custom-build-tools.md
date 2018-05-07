---
title: Outils de génération personnalisée de spécification | Documents Microsoft
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets
- VC.Project.VCCustomBuildTool.Outputs
- VC.Project.VCCustomBuildTool.Command
- VC.Project.VCCustomBuildTool.CommandLine
- VC.Project.VCCustomBuildTool.AdditionalDependencies
- VC.Project.VCCustomBuildTool.Message
- VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets
- VC.Project.VCCustomBuildTool.Description
- VC.Project.VCCustomBuildTool.AdditionalInputs
dev_langs:
- C++
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b8fc10d2a94ab4b26a47991d3dc8923afb28ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="specify-custom-build-tools"></a>Spécifiez les outils de génération personnalisée

A *outil de génération personnalisée* fournit le système de génération avec les informations nécessaires générer des fichiers d’entrée spécifiques. Un outil de génération personnalisée spécifie une commande à exécuter, une liste de fichiers d’entrée, une liste des fichiers de sortie générés par la commande et une description facultative de l’outil.

Pour obtenir des informations générales sur les outils de génération personnalisée et les étapes de génération personnalisée, consultez [présentation des étapes de génération personnalisée et des événements de Build](../ide/understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-custom-build-tool"></a>Pour spécifier un outil de génération personnalisée

1. Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [définition des propriétés de projet Visual C++](../ide/working-with-project-properties.md).

1. Choisissez **propriétés de Configuration** pour activer la **Configuration** boîte. Dans le **Configuration** , sélectionnez la configuration pour laquelle vous souhaitez spécifier un outil de génération personnalisée.

1. Dans **l’Explorateur de solutions**, sélectionnez le fichier d’entrée pour l’outil de génération personnalisée.

   Si le **outil de génération personnalisée** dossier n’apparaît pas, l’extension de fichier du fichier que vous avez sélectionné est associée à un outil par défaut. Par exemple, l’outil par défaut pour les fichiers .c et .cpp est le compilateur. Pour remplacer un paramètre d’outil par défaut, dans le **propriétés de Configuration** nœud, dans le **général** dossier, dans le **Type d’élément** propriété, choisissez **de génération personnalisée Outil**. Choisissez **appliquer** et **outil de génération personnalisée** nœud s’affiche.

1. Dans le **outil de génération personnalisée** nœud, dans le **général** dossier, spécifiez les propriétés associées personnalisé outil de génération :

   - Dans **dépendances supplémentaires**, spécifiez tous les fichiers supplémentaires au-delà de celle pour laquelle l’outil de génération personnalisée est défini (le fichier associé à l’outil de génération personnalisée est implicitement considéré comme une entrée de l’outil). Un des fichiers d’entrée supplémentaires n’est pas obligatoire pour un outil de génération personnalisée. Si vous avez plusieurs entrées supplémentaires, séparez-les par des points-virgules.

      Si un **dépendances supplémentaires** date du fichier est ultérieure à celle du fichier d’entrée, l’outil de génération personnalisée est exécuté. Si tous les de la **dépendances supplémentaires** fichiers plus anciens que le fichier d’entrée, et le fichier d’entrée est antérieure à la **sorties** fichier de propriétés, puis l’outil de génération personnalisée n’est pas exécutée.

      Par exemple, supposons que vous disposez d’un outil de génération personnalisée qui utilise MyInput.x en entrée et génère MyInput.cpp, et que MyInput.x inclut un fichier d’en-tête, MyHeader.h. Vous pouvez spécifier MyHeader.h comme dépendance d’entrée pour MyInput.x et le système de génération générera MyInput.cpp lorsqu’il est obsolète par rapport à MyInput.x ou MyHeader.h.

      Les dépendances d’entrée peuvent également vous assurer que vos outils de génération personnalisée doit s’exécuter dans l’ordre que vous le souhaitez. L’exemple précédent, supposons que MyHeader.h soit en fait la sortie d’un outil de génération personnalisée. MyHeader.h étant une dépendance de MyInput.x, le système de génération sera d’abord Myheader.h avant d’exécuter l’outil de génération personnalisée sur MyInput.x.

   - Dans **ligne de commande**, spécifiez une commande comme si vous le feriez à l’invite de commandes. Spécifiez une commande valide ou un fichier de commandes, et les entrées requises ou les fichiers de sortie. Spécifiez le **appeler** commande avant le nom d’un fichier de commandes afin de garantir que toutes les commandes suivantes sont exécutées.

      Plusieurs fichiers d’entrée et de sortie peuvent être spécifiés symboliquement avec les macros de MSBuild. Pour plus d’informations sur la façon de spécifier l’emplacement des fichiers ou les noms des groupes de fichiers, consultez [Macros commun pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).

      Étant donné que le caractère « % » est réservé à MSBuild, si vous spécifiez une variable d’environnement remplacez chaque **%** avec un caractère d’échappement le **% 25** séquence d’échappement hexadécimale. Par exemple, remplacez **%Windir%** avec **25WINDIR % 25**. MSBuild remplace chaque **% 25** séquence avec le **%** caractères avant d’accéder à la variable d’environnement.

   - Dans **Description**, entrez un message descriptif sur cet outil de génération personnalisée. Le message est imprimé sur le **sortie** fenêtre lorsque le système de génération traite cet outil.

   - Dans **sorties**, spécifiez le nom du fichier de sortie. Il s’agit d’une entrée requise ; sans une valeur pour cette propriété, l’outil de génération personnalisée se n'est pas. Si un outil de génération personnalisée possède plusieurs sorties, séparez les noms de fichiers par un point-virgule.

      Le nom du fichier de sortie doit être le même tel qu’il est spécifié dans le **ligne de commande** propriété. Le système de génération de projet recherchera le fichier et vérifiez sa date. Si le fichier de sortie est plus récent que le fichier d’entrée, ou si le fichier de sortie n’est pas trouvé, l’outil de génération personnalisée est exécutée. Si tous les de la **dépendances supplémentaires** fichiers plus anciens que le fichier d’entrée, et le fichier d’entrée est plus ancien que le fichier spécifié dans le **sorties** propriété, l’outil de génération personnalisée n’est pas exécutée.

Si vous souhaitez que le système de génération pour fonctionner sur un fichier de sortie généré par l’outil de génération personnalisée, vous devez l’ajouter manuellement au projet. L’outil de génération personnalisée mettra à jour le fichier pendant la génération.

## <a name="example"></a>Exemple

Supposons que vous souhaitez inclure un fichier nommé parser.l dans votre projet. Vous avez un analyseur lexical, **lexer.exe**, sur votre chemin exécutable. Vous souhaitez utiliser pour traiter les parser.l pour produire un fichier .c qui porte le même nom de base (parser.c).

Tout d’abord, ajoutez parser.l et parser.c au projet. Si les fichiers n’existent pas encore, ajoutez une référence aux fichiers. Créer un outil de génération personnalisée pour parser.l et entrez les informations suivantes dans le **commandes** propriété :

> **Analyseur lexical %(FullPath). \%(Filename) .c**

Cette commande exécute l’analyseur lexical sur parser.l et fournit en sortie parser.c dans le répertoire du projet.

Dans le **sorties** propriété, entrez les informations suivantes :

> **. \%(Filename) .c**

Lorsque vous générez le projet, le système de génération compare les horodatages de parser.l et parser.c. Si parser.l est plus récent, ou si parser.c n’existe pas, le système de génération exécute la valeur de la **ligne de commande** propriété à mettre à jour de parser.c. Étant donné que parser.c a également été ajouté au projet, le système de génération compile ensuite parser.c.

## <a name="see-also"></a>Voir aussi

[Macros courantes pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)  
[Dépannage des personnalisations de génération](../ide/troubleshooting-build-customizations.md)  
