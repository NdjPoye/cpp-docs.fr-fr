---
title: "Sp&#233;cification d&#39;&#233;v&#233;nements de build | Microsoft Docs"
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
  - "VC.Project.IVCEventTool.CommandLine"
  - "VC.Project.IVCEventTool.ExcludedFromBuild"
  - "VC.Project.IVCEventTool.Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "événements de build (C++)"
  - "événements de build (C++), spécifier"
  - "générations (C++), personnaliser C++"
  - "générations (C++), événements"
  - "étapes de génération personnalisée (C++), événements de build"
  - "événements (C++), build"
  - "événements post-build"
  - "événement avant l'édition des liens"
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sp&#233;cification d&#39;&#233;v&#233;nements de build
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser des événements de build pour spécifier des commandes qui s'exécutent avant le début de la génération, avant le processus d'édition des liens ou après la génération.  
  
 Les événements de build sont exécutés uniquement si la génération atteint ces étapes du processus de génération.  Si une erreur survient pendant la génération, l'événement *post\-build* ne se produit pas ; si l'erreur se produit avant la phase de liaison, ni l'événement *avant l'édition des liens* ni l'événement *post\-build* ne se produisent.  En outre, si aucun fichier ne doit être lié, l'événement *avant l'édition des liens* ne se produit pas.  L'événement *avant l'édition des liens* n'est pas non plus disponible dans les projets qui ne contiennent pas d'étape de liaison.  
  
 Si aucun fichier ne doit être généré, aucun événement de build ne se produit.  
  
 Pour obtenir des informations générales sur les événements de build, consultez [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md).  
  
### Pour spécifier un événement de build  
  
1.  Dans l'**Explorateur de solutions**, sélectionnez le projet pour lequel vous voulez spécifier l'événement de build.  
  
2.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
3.  Dans le dossier **Événements de build**, sélectionnez une page de propriétés d'événement de build.  
  
4.  Spécifiez les propriétés associées à l'événement de build :  
  
    -   Dans **Ligne de commande**, spécifiez une commande comme vous le feriez à une invite de commandes.  Spécifiez une commande ou un fichier de commandes valide, ainsi que les fichiers d'entrée ou de sortie requis.  Spécifiez la commande batch **call** avant le nom d'un fichier de commandes pour garantir l'exécution de toutes les commandes suivantes.  
  
         Il est possible de spécifier plusieurs fichiers d'entrée et de sortie symboliquement à l'aide de macros MSBuild.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] la spécification de l'emplacement de fichiers ou de noms de jeux de fichiers, consultez [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).  
  
         Dans la mesure où le caractère « % » est réservé à MSBuild, lorsque vous spécifiez une variable d'environnement, il convient de remplacer chaque caractère d'échappement **%** par la séquence d'échappement hexadécimale **%25**.  Par exemple, remplacez **%WINDIR%** par **%25WINDIR%25**.  MSBuild remplace chaque séquence **%25** par le caractère **%** avant d'accéder à la variable d'environnement.  
  
    -   Dans **Description**, tapez une description pour cet événement.  La description s'affichera dans la fenêtre **Sortie** lorsque cet événement se produit.  
  
    -   Dans **Exclu de la génération**, spécifiez **Oui** si vous ne voulez pas que l'événement soit exécuté.  
  
## Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)   
 [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)   
 [Dépannage des personnalisations de génération](../ide/troubleshooting-build-customizations.md)