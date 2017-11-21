---
title: "Spécification d’événements de Build | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
dev_langs: C++
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 43f12e28487a4e162a88eaf0881ac9e50391e1f4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-build-events"></a>Spécification d'événements de build
Vous pouvez utiliser des événements de build pour spécifier des commandes qui s’exécutent avant le démarrage, avant que le processus de liaison, ou après la génération.  
  
 Les événements de build sont exécutés uniquement si la build atteint ces étapes du processus de génération. Si une erreur se produit dans la build, la *post-build* événement n’a pas lieu ; si l’erreur se produit avant la phase de liaison, ni le *avant lien* ni le *post-build* événement sera se produit. En outre, si aucun fichier ne doit être lié, le *avant lien* événement n’a pas lieu. Le *avant lien* événement n’est pas également disponible dans les projets qui ne contiennent pas d’étape de liaison.  
  
 Si aucun fichier ne doit être généré, aucun événement de build ne se produit.  
  
 Pour obtenir des informations générales sur les événements de build, consultez [présentation des étapes de génération personnalisée et des événements de Build](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### <a name="to-specify-a-build-event"></a>Pour spécifier un événement de build  
  
1.  Dans l’**Explorateur de solutions**, sélectionnez le projet pour lequel vous voulez spécifier l’événement de build.  
  
2.  Ouvrez la boîte de dialogue **Pages de propriété** du projet. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
3.  Dans le **des événements de Build** dossier, sélectionnez une page de propriétés des événements de build.  
  
4.  Spécifiez les propriétés associées à l’événement de build :  
  
    -   Dans **ligne de commande**, spécifiez une commande comme si vous le feriez à l’invite de commandes. Spécifiez une commande valide ou un fichier de commandes, et les entrées requises ou les fichiers de sortie. Spécifiez le **appeler** commande avant le nom d’un fichier de commandes afin de garantir que toutes les commandes suivantes sont exécutées.  
  
         Plusieurs fichiers d’entrée et de sortie peuvent être spécifiés symboliquement avec les macros de MSBuild. [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)]spécifiant l’emplacement des fichiers ou les noms des groupes de fichiers, consultez [Macros commun pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Étant donné que le caractère « % » est réservé à MSBuild, si vous spécifiez une variable d’environnement remplacez chaque  **%**  avec un caractère d’échappement le **% 25** séquence d’échappement hexadécimale. Par exemple, remplacez **%Windir%** avec **25WINDIR % 25**. MSBuild remplace chaque **% 25** séquence avec le  **%**  caractères avant d’accéder à la variable d’environnement.  
  
    -   Dans **Description**, tapez une description pour cet événement. La description s’affichera dans le **sortie** fenêtre lorsque cet événement se produit.  
  
    -   Dans **exclu de la génération**, spécifiez **Oui** si vous ne souhaitez pas que l’événement à exécuter.  
  
## <a name="see-also"></a>Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de Build](../ide/understanding-custom-build-steps-and-build-events.md)   
 [Macros communs pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)   
 [Dépannage des personnalisations de génération](../ide/troubleshooting-build-customizations.md)